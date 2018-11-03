# Block

## Block 的实现

源码:
```objc
int main()
{
    void (^blk) (void) = ^ {
        printf("heihei");
    };
    blk();
    return 0;
}
```

block 结构体，本质为对象
```objc
struct __block_impl {
  void *isa;
  int Flags;
  int Reserved;
  void *FuncPtr;
};
```

底层实现：

```objc
struct __main_block_impl_0 {
  struct __block_impl impl;
  struct __main_block_desc_0* Desc;
  __main_block_impl_0(void *fp, struct __main_block_desc_0 *desc, int flags=0) {
    impl.isa = &_NSConcreteStackBlock;
    impl.Flags = flags;
    impl.FuncPtr = fp;
    Desc = desc;
  }
};

static void __main_block_func_0(struct __main_block_impl_0 *__cself) {
        printf("heihei");
}

static struct __main_block_desc_0 {
  size_t reserved;
  size_t Block_size;
} __main_block_desc_0_DATA = { 0, sizeof(struct __main_block_impl_0)};
```

调用:
```objc
int main()
{
    void (*blk) (void) = ((void (*)())&__main_block_impl_0((void *)__main_block_func_0, &__main_block_desc_0_DATA));
    ((void (*)(__block_impl *))((__block_impl *)blk)->FuncPtr)((__block_impl *)blk);
    return 0;
}
```

> 命名规则：根据 Block 语法所属的函数名 (main)，以及在该函数出现的顺序 (0)

## 一个 Block 的内存布局

```objc
struct Block_desc {
    size_t reserved;
    size_t Block_size;
}

struct Block_layout {
    void *isa;
    int flags;
    int reserved;
    void *FuncPtr;
    struct Block_desc *desc;
    /* Captured variables. */
    //...
}
```

## 在 Objective-C 语言中，一共有 3 种类型的 block：

- _NSConcreteGlobalBlock 全局的静态 block，不会访问任何外部变量。
- _NSConcreteStackBlock 保存在栈中的 block，当函数返回时会被销毁。
- _NSConcreteMallocBlock 保存在堆中的 block，当引用计数为 0 时会被销毁。


> 上面的例子中,由于 clang 改写的具体实现方式和 LLVM 不太一样，并且这里没有开启 ARC。所以这里我们看到 isa 指向的还是_NSConcreteStackBlock。但在 LLVM 的实现中，开启 ARC 时，block 应该是 _NSConcreteGlobalBlock 类型

