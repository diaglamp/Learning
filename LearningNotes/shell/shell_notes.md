
## 参数处理
### 常规使用
- $1 $2

### getopts 
shell命令行参数解析工具
无法清楚地记得每个位置对应的是什么参数

```bash
usage() {
    echo "Usage:"
    # ...
    exit -1
}

while getopts 'hj:m:s' OPT; do
    case $OPT in
        j) Jump_DIR="$OPTARG";;
        m) Move_DIR="$OPTARG";;
        u) short="true";;
        h) usage;;
        ?) usage;;
    esac
done

shift $(($OPTIND - 1))
echo $1

```

- `getopts`后面跟的字符串就是参数列表，每个字母代表一个选项
- 如果字母后面跟一个`:`就表示这个选项还会有一个值
- 如果字母没有跟随`:`就是开关型选项，不需要指定值
- `case`的最后一项是`?`，用来识别非法的选项，进行相应的操作
- `OPTARG` 用来获取当前选项的值
- `OPTIND` 表示当前选项在参数列表中的位移
- 当选项参数识别完成以后，我们就能识别剩余的参数了，我们可以使用`shift`进行位移，抹去选项参数。
- 位移的长度等于`case`循环结束后的`OPTIND - 1`，`OPTIND`的初始值为1，当选项参数处理结束后，其指向剩余参数的第一个。
- `getopts`在处理参数时，处理带值的选项参数，`OPTIND`加2；处理开关型变量时，`OPTIND`则加1。