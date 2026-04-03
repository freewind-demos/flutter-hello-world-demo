# Flutter 最小可运行应用（Hello World）

## 简介

用最少的 `MaterialApp` + `Scaffold` + `Text` 搭出一个能跑起来的 Flutter 应用，适合确认环境、工具链和首屏渲染是否正常。

## 快速开始

### 环境要求

本机已安装 Flutter SDK（建议 stable），终端可执行 `flutter doctor`，无阻塞性报错。

### 运行

在本 README 所在目录（项目根目录）执行：

```bash
flutter pub get
flutter run
```

按需指定设备，例如 `flutter run -d chrome` 或 `flutter run -d macos`，以 `flutter devices` 列出的为准。

## 概念讲解

### 第一部分：`runApp` 与 `MaterialApp`

`runApp` 把根 Widget 交给 Flutter 引擎；`MaterialApp` 提供 Material 风格的路由、主题与本地化等外壳。最简形态只需给一个 `home:`，先不必关心命名路由。

### 第二部分：`Scaffold` 与常用子部件

`Scaffold` 是单页的架子：可以放 `AppBar`、`body`、`FloatingActionButton` 等。这里只用 `body`，里面用 `Center` 把文字摆在中间。

示例（节选，完整见 `lib/main.dart`）：

```dart
void main() {
  runApp(
    MaterialApp(
      home: Scaffold(
        body: Center(
          child: Text('Hello, Flutter!'),
        ),
      ),
    ),
  );
}
```

## 完整示例

本仓库已是一棵完整 Flutter 工程树（含 `pubspec.yaml`、各平台目录）。逻辑集中在 `lib/main.dart`。若你只想对照「最小代码」，打开该文件即可。

## 注意事项

- 首次运行某平台时，Flutter 可能下载对应工具链，耗时会稍长。
- Web 与桌面端也支持运行；若有插件再核对是否支持目标平台。

## 完整讲解（中文）

可以把 Flutter 应用想成一棵树：最上面是 `MaterialApp`，下面挂页面 `Scaffold`，再往下是各种「小积木」Widget。Hello World 在这棵树里只做三件事：**选一个根**、**给一页容器**、**在中间放一行字**。你一旦能稳定看到 `Hello, Flutter!`，说明 Dart 编译、Flutter 引擎到目标设备的链路已经打通，后面学布局、路由、状态管理，都只是在这棵树上继续加枝、换叶，而不用再怀疑「工具装没装好」这一类底层问题。
