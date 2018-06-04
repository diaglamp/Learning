## 编译优化

### 名词解析
- Clang 编译器前端
- LLVM (Low Level virtual machine) 编译器后端


### Clang 
- 语法分析
- 语义分析
- 生成中间代码

### LLVM

- 机器无关代码优化
- 生成机器语言
- 机器相关代码优化

- BitCode生成
- 链接期优化
- 针对不同架构生成不同机器码

### 编译流程

执行一次 Xcode build

- 编译信息写入辅助文件，创建编译后的文件架构（name.app）
- 处理文件打包信息（entitlements）
- 执行编译前脚本
- 编译文件 `CompileC` `clang`
- 链接Framework
- 编译 xib 文件
- 拷贝xib、图片等资源
- 编译 ImageAssets
- 处理info.plist
- 创建 .app 并签名
