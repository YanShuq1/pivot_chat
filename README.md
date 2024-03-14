# pivot_chat

Pivot Studio 打造的聊天软件。

## Getting Started

### Set up your environment

Fork the xhzq233/pivot_chat repo into your own GitHub account.

Clone the forked repo locally using the method of your choice. GitHub Desktop is simplest.

If you cloned the repo using SSH, you'll need to configure the upstream remote for xhzq233/pivot_chat. This will allow you to sync changes made in xhzq233/pivot_chat with the fork:

- cd pivot_chat
- Specify a new remote upstream repository (xhzq233/pivot_chat) that will be synced with the fork.
  SSH: git remote add upstream git@github.com:xhzq233/pivot_chat.git
- Verify the new upstream repository you've specified for your fork.
  `git remote -v`

Then you can commit and push your changes to your forked repo and create a pull request to xhzq233/pivot_chat.

let's start coding🚀!

### Set up your editor

`dart format` change to -l120

![Screenshot 2023-07-09 at 15.51.34](README.assets/dart_line_length.png)

## 项目结构

- lib/theme.dart：主题配置，设计给出
- lib/assets.dart：资源文件，包括图片、颜色、字体等，如
  `const kPCLogo = 'assets/images/logo.png'`
- lib/pages/xxx: 各个页面以及各自需要的私有model
> 加前缀的原因是避免命名冲突与辨识度。
> Note: 以下为示例
> - lib/pages/dev/dev_page.dart: 页面，类名为LoginPage
> - lib/pages/dev/dev_vm.dart: ViewModel
> - lib/pages/dev/xxx_widget.dart: 页面的组件，一般不需要导出，以`_`开头，如\_LoginButton，以part形式导入到page.dart中

## 项目规范

### Debug

- 尽量使用assert来保证你所认为的代码的正确性，例如：

```dart
// here i assume the image size must be greater than 0
assert(_kDefaultImageSize > 0);
```

### Commit规范

- Commit提交前确保能编过（特殊情况合作解决编译问题除外）
- Commit粒度尽量细，尽量不要出现特大Commit
- 养成勤拉分支的习惯，做新的东西拉新的分支；

## Ignore

默认ignore了**/*.g.dart，避免代码提交时冲突，副作用是需要手动运行`dart pub run build_runner build`来生成代码

## 编写网络API

见/lib/manager/network/pc_network_manager.dart中的example
