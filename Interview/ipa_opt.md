# 包大小优化

## 理论

### IPA 包结构

Adhoc 包，AppStore包，iTunes包 除了Payload外其他信息有差别

- SymbolMaps
- Symbols
- Payload
    - 可执行文件 Mach-O
    - 资源文件（图片、音频、视频，第三方bundle，plist等）
    - 文件签名


### Mach-O 结构
- Fat Header 多种架构的头，包含架构信息
- Mach Header 可执行文件头，包含架构信息，文件类型，LC的数量和大小
- Load Commands 
    - Segment 的 metadata ：虚拟内存中的偏移地址和大小、读写执行权限
    - Section 的 metadata ：所在Segment、虚拟内存偏移和大小
    - 符号表、动态符号表的描述 ：偏移地址、符号数量、字符串表偏移大小
    - 动态连接器信息 ：dyld路径
    - UUID
    - 所支持最低的操作系统
    - main 函数的入口地址
    - 加密信息
    - 需要加载的动态库信息 ：动态库列表、当前版本、兼容版本、路径
- // Segments
- __PAGEZERO 
    - contains no data
- __TEXT <br>
    executable code, read-only data, sharable memory
    - // Sections
    - __text
    - __stub
    - __stub_helper
        - __cstring
    - __objc_methname
    - __objc_classname
    - __objc_methtype
    - __ustring
    - __const
- __DATA <br>
    writable data, read write permission, copy on write COW
    - __nl_symbol_ptr : Non-Lazy Symbol Pointers
    - __la_symbol_ptr : Lazy Symbol Pointers
    - __mod_init_func : Module Init Func Pointer
    - __const 
    - __cstring : ObjC CFStrings
    - __objc_classlist
    - __objc_catlist
    - __objc_nlcatlist
    - __objc_protolist
    - __objc_imageinfo
    - __objc_const
    - __objc_selfrefs
    - __objc_protorefs
    - __objc_classrefs
    - __objc_ivar
    - __objc_data
    - __data
- __LINKEDIT <br>
    raw data userd by the dynamic linker, such as symbol, string and relocation table entry
    - Dynamic Loader Info
        - Rebase Info
        - Binding Info
        - Weak Binding Info
        - Lazy Binding Info
        - Export Info
    - Function Starts 
    - Data in Code Entries 
    - Symbol Table
    - Dynamic Symbol Table
    - String Table
    - Code Signature


## 分析

### LinkMap 文件结构
- Object files
    - .o文件 -- .m编译后的产物
    - 文件路径
    - 文件编号
- Sections
    - Address 地址
    - Size 大小
    - Segment 段
    - Section 节
- Symbols
    - Address 地址
    - Size 大小
    - File 文件编号
    - Name 类名-方法名
- Dead Stripped Symbols
    - dead
    - Size 
    - File 
    - Name

Object files 中有标记各个文件的编号，通过文件编号可以再 Symbols 中找到所有字段的所占的大小。然后计算出各个文件的大小。

## 优化方法

- 优化资源
    - 去除无用资源
    - 资源压缩
        - 压缩图片
        - 尽量使用8bit的图片
        - 压缩音频 -- 使用ACC or MP3
    - 对app内的资源按使用频率进行分级，不常用的资源可以需要的时候再加载
    - 使用Asset Catalogs
        - 使用Asset可以减少在指定设备的ipa中只使用@2x or @3x图片，而不需要都带上
    - 动态资源下载
        - 使用率较少的资源
- 编译优化
    - 开启编译优化
    - 避免编译多个架构
- 可执行文件优化
    - 去除无用代码
        - 没有被使用的类
        - 无效的import
        - 无效方法
        - 无效属性
    - 去除多余的库 （大头）
    - 去除代码数据 -- 代码文件的压缩率比较低
    - 使用MRC管理内存 -- 意义不大
	

### 关于图片格式的选择
- PNG无损、加载和显示会更快
- JPG有损，但大图时会小很多，显示时需要额外的复杂的解码算法
- 对于照片和大图选择JPG；小图、要求无损、有透明通道使用PNG




## 参考链接：

[Reducing the size of my App - 官方文档](https://developer.apple.com/library/content/qa/qa1795/_index.html)

[Mach-O Programming Topics - 官方文档](https://developer.apple.com/library/archive/documentation/DeveloperTools/Conceptual/MachOTopics/1-Articles/building_files.html#//apple_ref/doc/uid/TP40001828-96838-BABBHEIC)

[OS X ABI Mach-O File Format Reference - 官方文档](http://of685p9vy.bkt.clouddn.com/OS%20X%20ABI%20Mach-O%20File%20Format%20Reference.pdf)

[iOS可执行文件瘦身方法 - Bang](https://blog.cnbang.net/tech/2544/)

[深入剖析Macho - SatanWoo](http://satanwoo.github.io/2017/06/13/Macho-1/)