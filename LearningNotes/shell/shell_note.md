
# SEHLL 学习笔记

## 调试相关

### 调试开关

调试开关
```
#set -u  遇到不存在的变量时报错，并停止执行
#set -x  在运行结果之前，先输出执行的那一行命令。
#set -e  脚本只要发生错误，就终止执行。
#set -o pipefail  只要一个子命令失败，整个管道命令就失败

# 调试选项
set -exu
set -o pipefail
# 生产选项
# set -e
# set -o pipefail
```

调试技巧
```
# 某些命令的非零返回值可能不表示失败，或者开发者希望在命令失败的情况下，脚本继续执行下去。
# set +e
# command1
# set -e

#set -u 不能用于入参 optional 的脚本

# 调试技巧
# sh -n  只检查脚本语法，但不执行  sh -n test.sh
# 调试时开启 set -x
```