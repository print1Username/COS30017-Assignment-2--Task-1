# COS30017 Assignment 2 - Task 1

这是 **COS30017 Software Development for Mobile Devices** 的 Kotlin + XML Android Assignment 2 项目。

目前本仓库已经完成：

- **Task 1 - Sandwich App**

> **语言：中文**  
> [English Version / 英文版](README.md)

---

## 1. 项目简介

本 Assignment 使用：

- **Android Studio**
- **Kotlin**
- **XML Views**
- **Gradle**
- **Git / GitHub**

项目使用的是 **Empty Views Activity**，不是 Jetpack Compose。

### Task 1 - Sandwich App

Sandwich App 可以让用户：

- 选择 Sandwich Filling
- 选择 Side
- 选择 Sandwich Size
- 实时查看 Total Price
- 查看最新的 Filling 和 Side 选择
- Place Order 并查看 Itemized Bill
- Reset 所有选择

程序按照 Assignment 的要求实现：

- 6 inch、9 inch、12 inch
- 每个 Sandwich 包含 1 个免费 Filling
- 每个 Sandwich 包含 1 个免费 Side
- 每个类别中，**价格最低的已选择项目免费**
- 最多选择 3 个 Filling
- Side 没有限制
- 至少选择 1 个 Filling 才能 Place Order

---

# 2. 开发环境要求

开始项目之前，请安装以下软件。

## 必需软件

### Android Studio

安装 Android Studio：

https://developer.android.com/studio

安装过程中，请确保 Android SDK 和 Android 开发所需要的组件已经安装。

### Git

安装 Git：

https://git-scm.com/downloads

安装完成后，在 Terminal / Command Prompt 中执行：

```bash
git --version
```

如果出现 Git 的版本号，说明安装成功。

### GitHub Account

建议使用 GitHub 保存和管理项目：

https://github.com/

---

# 3. Android Studio 配置

对于新手，最简单的方式是让项目使用项目自身 Gradle 配置中指定的版本。

## 第一步：打开项目

1. 打开 Android Studio。
2. 选择 **Open**。
3. 选择项目文件夹。
4. 等待 Android Studio 完成 Indexing。
5. 等待 Gradle Sync 完成。

不要因为 Android Studio 提示有更新，就立刻把 Gradle、Kotlin 或 Android Gradle Plugin 全部升级。学生项目最常见的灾难之一，就是一个原本能运行的项目被“顺手更新”成了版本考古现场。

## 第二步：检查 Android SDK

打开：

**Android Studio → Settings → Languages & Frameworks → Android SDK**

macOS 中对应的是：

**Android Studio → Settings / Preferences → Languages & Frameworks → Android SDK**

确保项目需要的 Android SDK Platform 和 SDK Tools 已经安装。

如果项目的 `compileSdk` 指定了特定版本，请在 SDK Manager 中安装对应版本。

## 第三步：检查 JDK

Android Studio 的 Gradle 项目会使用 Gradle 配置的 JDK。

打开：

**File → Settings → Build, Execution, Deployment → Build Tools → Gradle**

检查 **Gradle JDK**。

如果项目已经可以正常 Build，就不要为了“看起来更新”而随便修改 JDK。

---

# 4. 项目结构

主要结构通常类似：

```text
project-root/
├── app/
│   ├── src/
│   │   └── main/
│   │       ├── java/ 或 kotlin/
│   │       ├── res/
│   │       │   ├── drawable/
│   │       │   ├── layout/
│   │       │   ├── mipmap/
│   │       │   └── values/
│   │       └── AndroidManifest.xml
│   ├── build.gradle.kts
│   └── ...
├── gradle/
├── build.gradle.kts
├── settings.gradle.kts
├── gradlew
├── gradlew.bat
└── README.md
```

具体 Package Name 和文件名称可能根据 Android Studio 项目配置有所不同。

### 重要文件夹

| 文件夹 | 用途 |
|---|---|
| `app/src/main/java` 或 `kotlin` | Kotlin 源代码 |
| `app/src/main/res/layout` | XML 页面布局 |
| `app/src/main/res/drawable` | 图片和 Drawable 资源 |
| `app/src/main/res/values` | Strings、Colors、Themes、Dimensions 等 |
| `app/src/main/AndroidManifest.xml` | Application 和 Activity 配置 |
| `gradle` | Gradle Wrapper 配置 |

---

# 5. 从 GitHub Clone 项目

如果项目已经上传到 GitHub，可以打开 Terminal：

```bash
git clone <repository-url>
```

例如：

```bash
git clone https://github.com/your-username/your-repository.git
```

进入项目文件夹：

```bash
cd your-repository
```

然后使用 Android Studio 打开这个文件夹。

---

## 也可以直接通过 Android Studio Clone

1. 打开 Android Studio。
2. 点击 **Get from VCS**。
3. 选择 **Git**。
4. 输入 GitHub Repository URL。
5. 选择本地保存位置。
6. 点击 **Clone**。
7. 等待 Gradle Sync。

---

# 6. 如何运行 Android App

Android App 通常有两种运行方式：

1. Android Emulator
2. 实体 Android 手机

---

## 方法 A：Android Emulator

### 创建 Emulator

在 Android Studio：

**Tools → Device Manager**

然后：

1. 点击 **Create Device**。
2. 选择手机型号。
3. 选择或下载合适的 Android System Image。
4. 完成创建。
5. 启动 Emulator。

### 运行项目

1. 打开 Android Studio。
2. 等待 Gradle Sync 完成。
3. 确认 Run Configuration 是 `app`。
4. 选择刚刚启动的 Emulator。
5. 点击 **Run ▶**。

如果出现：

```text
No target device found
```

通常不代表项目代码有问题。

它一般表示 Android Studio 当前没有找到：

- 正在运行的 Emulator，或者
- 已连接的实体 Android Device

解决方法：

1. 打开 **Tools → Device Manager**。
2. 启动 Emulator。
3. 等待 Emulator 完全启动。
4. 再点击 **Run ▶**。

---

## 方法 B：使用实体 Android 手机

如果想使用真实 Android 手机：

1. 打开手机的 **Developer Options**。
2. 开启 **USB Debugging**。
3. 使用 USB 连接电脑和手机。
4. 手机出现授权提示时选择允许。
5. 等待 Android Studio 检测手机。
6. 在 Android Studio 的 Device Selector 中选择手机。
7. 点击 **Run ▶**。

如果检测不到手机，请检查：

- USB Cable
- USB Debugging
- 手机授权
- Windows 下的 Device Driver（如果需要）

---

# 7. 如何 Build 项目

运行之前，可以先检查项目能否成功编译。

Android Studio：

**Build → Make Project**

如果 Build 成功，说明 Kotlin 和 Android Resources 基本能够正常编译。

也可以使用 Gradle Wrapper。

### Windows

```bash
gradlew.bat build
```

### macOS / Linux

```bash
./gradlew build
```

建议优先使用 Gradle Wrapper，因为它会使用项目本身指定的 Gradle 版本。

---

# 8. Git 新手指南

Git 的作用是记录项目修改，让你可以：

- 查看修改
- 保存不同版本
- 回到之前的版本
- 与 GitHub 同步项目

最基本的流程：

```text
修改文件
   ↓
检查修改
   ↓
Add
   ↓
Commit
   ↓
Push 到 GitHub
```

---

## 查看当前修改

```bash
git status
```

这个命令可以查看：

- 哪些文件被修改
- 哪些文件是新文件
- 哪些文件还没有被 Git Tracking

---

## Add 文件

添加所有修改：

```bash
git add .
```

也可以只添加一个文件：

```bash
git add README.md
```

---

## Commit

```bash
git commit -m "Complete Task 1"
```

Commit Message 应该描述这次修改的内容。

例如：

```bash
git commit -m "Update sandwich pricing logic"
```

```bash
git commit -m "Improve Task 1 layout"
```

```bash
git commit -m "Add project documentation"
```

---

## Push 到 GitHub

```bash
git push
```

如果是第一次 Push 新 Branch，可能需要：

```bash
git push -u origin main
```

---

## Pull 最新代码

开始工作前，可以先：

```bash
git pull
```

这样可以获取 GitHub 上最新的项目修改。

---

# 9. 推荐 Git 工作流程

Assignment 开发时，可以使用一个非常简单的流程。

开始工作：

```bash
git pull
```

修改 Android Studio 中的代码。

完成后：

```bash
git status
git add .
git commit -m "Describe the change"
git push
```

例如：

```bash
git pull
```

修改 Sandwich App。

然后：

```bash
git status
git add .
git commit -m "Fix sandwich total calculation"
git push
```

不要每按一次键就 Commit。Git 是版本控制系统，不是监控摄像头。

---

# 10. 哪些文件不应该上传 GitHub

Android Studio 会产生一些 Build 文件和电脑本地配置文件。

这些文件通常不应该提交到 GitHub。

项目应该包含合适的 `.gitignore`。

常见需要忽略的内容：

```text
.gradle/
build/
local.properties
.idea/
*.iml
```

具体 `.gitignore` 内容会根据项目和 Android Studio 版本有所不同。

### 不要提交：

- API Keys
- Passwords
- Personal Credentials
- 电脑本地路径
- 大型 Generated Build Files
- Local SDK Configuration

---

# 11. Task 1 功能规则

Sandwich App 按照 Assignment 要求实现。

## Filling Price

| Filling | Price |
|---|---:|
| Ham | RM 2.50 |
| Roasted Chicken | RM 2.00 |
| Beef Steak | RM 4.50 |
| Grilled Salmon | RM 3.70 |
| Kebab | RM 4.00 |

## Side Price

| Side | Price |
|---|---:|
| Tomato | RM 1.00 |
| Lettuce | RM 1.20 |
| Onion | RM 0.50 |
| Cheese | RM 1.50 |

## Size Price

| Size | Price |
|---|---:|
| 6 inch | RM 7.00 |
| 9 inch | RM 9.50 |
| 12 inch | RM 13.00 |

---

## Free Item Rule

每个 Sandwich Size 包含：

- 1 个免费 Filling
- 1 个免费 Side

注意：

**免费项目不是第一个选择的项目，而是该类别中价格最低的已选择项目。**

例如：

```text
Size: 9 inch                 RM 9.50

Fillings:
    Beef Steak               RM 4.50
    Roasted Chicken          FREE

Sides:
    Cheese                   RM 1.50
    Tomato                   FREE
```

Total：

```text
RM 9.50 + RM 4.50 + RM 1.50
= RM 15.50
```

---

## Filling 最大数量

最多可以选择 **3 个 Filling**。

当用户已经选择 3 个 Filling 后：

- 剩余 Filling Checkboxes 会被 Disable

Side 没有数量限制。

---

## Place Order 验证

用户必须至少选择一个 Filling。

如果没有选择 Filling：

- 不允许下单
- 显示 Error AlertDialog

如果有 Filling：

- 正常生成 Itemized Billing

---

## Total 实时更新

以下内容发生变化时，Total 都会重新计算：

- Filling
- Side
- Size

这样 UI 上显示的 Total 会始终与当前选择保持一致。

---

# 12. Assignment 中的一个特殊问题

Assignment 文字要求写的是：

> Default size is 6 inch = RM 7.00.

但是 Figure 1 的初始 Total 显示为：

```text
RM 0.00
```

本项目按照**文字要求**实现：

```text
Default size = 6 inch
Default size price = RM 7.00
```

如果 Lecturer 在 Demo 或 Report 中询问，可以说明：

**实现遵循了 Assignment 的 written specification，而不是与文字要求冲突的 Figure 1 初始显示。**

---

# 13. 常见问题

## 问题：`No target device found`

通常意味着 Android Studio 找不到可以运行 App 的设备。

解决：

1. 打开 **Tools → Device Manager**。
2. 启动一个 Emulator。
3. 等待 Emulator 完全启动。
4. 再次 Run。

---

## 问题：`Android resource linking failed`

通常表示：

- XML Resource 有问题
- Manifest 有问题
- Resource Name 写错
- Resource 不存在
- `@string/...` 引用错误
- `@drawable/...` 引用错误

检查：

- XML Syntax
- Resource Name
- `@string/...`
- `@drawable/...`
- `AndroidManifest.xml`
- `res/values/strings.xml`

然后执行：

**Build → Make Project**

重点查看 Error 中**最前面的主要 AAPT 错误**。

后面很多错误可能只是第一个错误造成的连锁反应。

---

## 问题：Gradle Sync Failed

可以检查：

1. Internet Connection
2. Android Studio 是否还在加载
3. Gradle Error Message
4. Android SDK 是否安装
5. Gradle / Kotlin / Android Gradle Plugin 版本

如果项目之前能够正常运行，不要随便升级 Gradle、Kotlin 或 Android Gradle Plugin。

---

## 问题：Build 成功，但是不能 Run

检查：

- Emulator 是否启动
- 手机是否连接
- 手机是否允许 USB Debugging
- Run Configuration 是否选择 `app`
- Device Selector 中是否出现设备

---

# 14. 新手第一次运行项目的完整流程

如果你完全不知道从哪里开始，可以按照下面的顺序。

### Step 1

Clone GitHub Repository：

```bash
git clone <repository-url>
```

### Step 2

使用 Android Studio 打开项目。

### Step 3

等待 Gradle Sync。

### Step 4

如果出现 SDK / JDK 问题，再检查 Android Studio 配置。

### Step 5

打开：

**Tools → Device Manager**

创建并启动 Emulator。

### Step 6

执行：

**Build → Make Project**

### Step 7

选择 Emulator。

### Step 8

点击：

**Run ▶**

### Step 9

测试 Sandwich App。

### Step 10

查看 Git 修改：

```bash
git status
```

### Step 11

提交：

```bash
git add .
git commit -m "Describe the change"
git push
```

这个流程故意设计得很无聊，因为无聊的开发流程通常比“我改了一个 Gradle 文件然后整个项目爆炸”可靠得多。

---

# 15. Assignment Report

Assignment Report 应包含：

- Title：**Submission for Assignment 02**
- Student Name
- Student ID
- Task 1 Screenshots
- Task 2 Screenshots
- Relevant Kotlin Source Code
- Task 1 XML Layout Code
- Properly formatted code
- White background code presentation
- 不需要 Table of Contents

最终请按照 Lecturer 的 Assignment Requirements，通过 Canvas 提交。

---

# 16. README 语言版本

- **English README：** `README.md`
- **中文版 README：** `README.zh-CN.md`

两个文件可以互相切换：

[English README](README.md) | [中文 README](README.zh-CN.md)

---

# 17. License

本仓库属于 COS30017 学术 Assignment。

仅用于教育和 Assessment purposes。
