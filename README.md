# COS30017 Assignment 2 - Task 1

A Kotlin and XML Android application developed for **COS30017 Software Development for Mobile Devices**.


> **Language:** English  
> [中文版 / Chinese Version](README.zh-CN.md)

---

## 1. Project Overview

This assignment is developed using:

- **Android Studio**
- **Kotlin**
- **XML Views**
- **Gradle**
- **Git / GitHub**

The project uses an **Empty Views Activity** rather than Jetpack Compose.

### Task 1 - Sandwich App

The Sandwich App allows users to:

- Select sandwich fillings
- Select sandwich sides
- Select a sandwich size
- View the total price in real time
- See the latest filling and side selection
- Place an order and view an itemized bill
- Reset all selections

The pricing and selection logic follows the assignment specification, including:

- 6 inch, 9 inch, and 12 inch sizes
- One free filling
- One free side
- The **cheapest selected item** in each category is free
- Maximum of 3 fillings
- Unlimited sides
- At least one filling is required before placing an order

---

# 2. Requirements

Before starting the project, install the following software.

## Required

### Android Studio

Install a recent stable version of Android Studio:

https://developer.android.com/studio

During installation, make sure the Android SDK and required Android development components are installed.

### Git

Install Git:

https://git-scm.com/downloads

After installation, verify it from a terminal:

```bash
git --version
```

You should see a Git version number.

### GitHub Account

A GitHub account is recommended for storing and submitting the project repository:

https://github.com/

---

# 3. Android Studio Configuration

The easiest approach for beginners is to let the project use the versions specified by its Gradle configuration.

## Step 1 - Open the project

1. Start Android Studio.
2. Select **Open**.
3. Select the project folder.
4. Wait for Android Studio to finish indexing.
5. Allow Gradle Sync to complete.

Do not immediately start changing Gradle versions just because Android Studio suggests something newer. Version mismatches are one of the classic ways to turn a working student project into an archaeological excavation.

## Step 2 - Check the SDK

Open:

**Android Studio → Settings → Languages & Frameworks → Android SDK**

On macOS, the equivalent is:

**Android Studio → Settings / Preferences → Languages & Frameworks → Android SDK**

Make sure an Android SDK platform and the required SDK tools are installed.

If the project specifies a particular `compileSdk`, install that SDK version through the SDK Manager.

## Step 3 - Check the JDK

Android Studio projects normally use the JDK configured for Gradle.

Check:

**File → Settings → Build, Execution, Deployment → Build Tools → Gradle**

Make sure the selected Gradle JDK is compatible with the project's Gradle and Android Gradle Plugin versions.

If the project already builds successfully, avoid changing the JDK without a reason.

---

# 4. Project Structure

The important files are generally located in:

```text
project-root/
├── app/
│   ├── src/
│   │   └── main/
│   │       ├── java/ or kotlin/
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

The exact package names and file names may differ depending on the Android Studio project configuration.

### Important folders

| Folder | Purpose |
|---|---|
| `app/src/main/java` or `kotlin` | Kotlin source code |
| `app/src/main/res/layout` | XML screen layouts |
| `app/src/main/res/drawable` | Images and drawable resources |
| `app/src/main/res/values` | Strings, colors, themes, dimensions, etc. |
| `app/src/main/AndroidManifest.xml` | Application and activity configuration |
| `gradle` | Gradle wrapper configuration |

---

# 5. Clone the Repository

If you are starting from GitHub, open a terminal and run:

```bash
git clone <repository-url>
```

For example:

```bash
git clone https://github.com/your-username/your-repository.git
```

Then enter the project folder:

```bash
cd your-repository
```

Open this folder in Android Studio.

### Alternative: Clone directly from Android Studio

1. Open Android Studio.
2. Select **Get from VCS**.
3. Select **Git**.
4. Enter the repository URL.
5. Choose a local folder.
6. Click **Clone**.
7. Wait for Gradle Sync.

---

# 6. Running the Application

There are two main ways to run an Android application:

1. Android Emulator
2. Physical Android device

---

## Option A - Android Emulator

### Create an emulator

In Android Studio:

**Tools → Device Manager**

Then:

1. Click **Create Device**.
2. Select a phone model.
3. Select or download a suitable Android system image.
4. Finish the setup.
5. Start the emulator.

### Run the project

1. Open the project in Android Studio.
2. Wait for Gradle Sync to finish.
3. Select the `app` run configuration.
4. Select the emulator.
5. Click the **Run ▶** button.

If Android Studio displays:

```text
No target device found
```

the project may be fine. It usually means that no emulator or physical Android device is currently available.

Start an emulator from **Device Manager**, then run the application again.

---

## Option B - Physical Android Device

To use a real Android phone:

1. Enable **Developer Options** on the phone.
2. Enable **USB Debugging**.
3. Connect the phone to the computer using USB.
4. Accept the debugging permission on the phone.
5. Wait for Android Studio to detect the device.
6. Select the device in the Android Studio device selector.
7. Click **Run ▶**.

If the device is not detected, check the USB cable, USB debugging permission, and device drivers where applicable.

---

# 7. Build the Project

Before running the application, it is useful to check whether the project can compile.

In Android Studio:

**Build → Make Project**

A successful build means the source code and Android resources can be compiled successfully.

You can also use the Gradle wrapper from a terminal.

### Windows

```bash
gradlew.bat build
```

### macOS / Linux

```bash
./gradlew build
```

The Gradle wrapper is preferred because it uses the Gradle version configured by the project.

---

# 8. Git Basics for Beginners

Git records changes to the project so that previous versions can be tracked and shared.

A simple workflow is:

```text
Edit files
   ↓
Check changes
   ↓
Add changes
   ↓
Commit
   ↓
Push to GitHub
```

---

## Check the current status

```bash
git status
```

This shows modified, added, and untracked files.

---

## Add files

To add all relevant changes:

```bash
git add .
```

Or add a specific file:

```bash
git add README.md
```

---

## Commit changes

```bash
git commit -m "Complete Task 1"
```

A commit message should describe what changed.

Examples:

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

## Push to GitHub

```bash
git push
```

If this is the first push for a new branch, Git may ask you to configure the upstream branch.

A common command is:

```bash
git push -u origin main
```

---

## Pull the latest changes

Before continuing work on an existing repository:

```bash
git pull
```

This downloads and integrates the latest changes from the remote repository.

---

# 9. Recommended Git Workflow

For assignment development, a simple workflow is enough:

```bash
git status
git add .
git commit -m "Describe the change"
git push
```

Before starting work:

```bash
git pull
```

A practical example:

```bash
git pull
```

Make changes in Android Studio.

Then:

```bash
git status
git add .
git commit -m "Fix sandwich total calculation"
git push
```

Avoid committing every tiny keystroke. Git is a version control system, not a surveillance camera.

---

# 10. Files That Should Not Be Committed

Android Studio generates build and machine-specific files that generally should not be uploaded to GitHub.

The repository should contain an appropriate `.gitignore`.

Common ignored files/folders include:

```text
.gradle/
build/
local.properties
.idea/
*.iml
```

The exact `.gitignore` depends on the project and Android Studio version.

### Important

Do not commit:

- API keys
- Passwords
- Personal credentials
- Machine-specific paths
- Large generated build files
- Local SDK configuration

---

# 11. Task 1 Functional Rules

The Sandwich App follows the assignment requirements.

## Filling prices

| Filling | Price |
|---|---:|
| Ham | RM 2.50 |
| Roasted Chicken | RM 2.00 |
| Beef Steak | RM 4.50 |
| Grilled Salmon | RM 3.70 |
| Kebab | RM 4.00 |

## Side prices

| Side | Price |
|---|---:|
| Tomato | RM 1.00 |
| Lettuce | RM 1.20 |
| Onion | RM 0.50 |
| Cheese | RM 1.50 |

## Size prices

| Size | Price |
|---|---:|
| 6 inch | RM 7.00 |
| 9 inch | RM 9.50 |
| 12 inch | RM 13.00 |

---

## Free Item Rule

Each sandwich size includes:

- 1 free filling
- 1 free side

The free item is the **cheapest selected item** in that category.

For example:

```text
Size: 9 inch                 RM 9.50
Fillings:
    Beef Steak               RM 4.50
    Roasted Chicken          FREE

Sides:
    Cheese                   RM 1.50
    Tomato                   FREE
```

Total:

```text
RM 9.50 + RM 4.50 + RM 1.50
= RM 15.50
```

---

## Filling Limit

A maximum of **3 fillings** can be selected.

When 3 fillings have been selected, the remaining filling checkboxes are disabled.

Sides do not have a selection limit.

---

## Place Order Validation

The user must select at least one filling.

If no filling is selected, the application displays an error dialog instead of creating an order.

---

## Real-Time Total

The total is recalculated whenever the user changes:

- Filling selection
- Side selection
- Sandwich size

This keeps the displayed total synchronized with the current selections.

---

# 12. Important Assignment Note

The assignment text states:

> Default size is 6 inch = RM 7.00.

However, the provided Figure 1 reportedly shows an initial total of **RM 0.00**.

For the implementation, the written requirement is followed:

```text
Default size = 6 inch
Default size price = RM 7.00
```

If this difference is discussed during assessment, explain that the written specification was followed over the conflicting screenshot.

---

# 13. Common Problems

## Problem: `No target device found`

This usually means Android Studio cannot find an available emulator or physical Android device.

Solution:

1. Open **Tools → Device Manager**.
2. Start an emulator.
3. Wait for it to boot.
4. Run the project again.

---

## Problem: `Android resource linking failed`

This usually indicates a problem in an XML resource, manifest entry, resource name, or missing resource.

Check:

- XML syntax
- Resource names
- `@string/...` references
- `@drawable/...` references
- `AndroidManifest.xml`
- `res/values/strings.xml`

Then run:

**Build → Make Project**

Read the **first meaningful AAPT error** rather than chasing every line of the error output. Later errors are often just casualties of the first mistake.

---

## Problem: Gradle Sync failed

Try:

1. Check your internet connection.
2. Wait for Android Studio to finish loading.
3. Check the Gradle error message.
4. Make sure the required SDK is installed.
5. Avoid randomly upgrading Gradle, Kotlin, or Android Gradle Plugin versions.

If the project worked previously, restore the project configuration before changing versions.

---

## Problem: App builds but does not run

Check:

- An emulator is running, or
- A physical device is connected.
- The correct run configuration is selected.
- The device appears in Android Studio's device selector.

---

# 14. Suggested Development Workflow

For a new developer joining the project:

### Step 1

Clone the repository:

```bash
git clone <repository-url>
```

### Step 2

Open the project in Android Studio.

### Step 3

Wait for Gradle Sync.

### Step 4

Check the Android SDK and Gradle JDK if necessary.

### Step 5

Create/start an emulator from:

**Tools → Device Manager**

### Step 6

Build the project:

**Build → Make Project**

### Step 7

Run the application:

**Run ▶**

### Step 8

Test the functionality.

### Step 9

Check Git changes:

```bash
git status
```

### Step 10

Commit and push:

```bash
git add .
git commit -m "Describe the change"
git push
```

This is deliberately boring. Boring development workflows are usually the ones that don't set your project on fire.

---

# 15. Assignment Report

The assignment report should include:

- Title: **Submission for Assignment 02**
- Student name
- Student ID
- Task 1 screenshots
- Task 2 screenshots
- Relevant Kotlin source code
- XML layout code for Task 1
- Properly formatted code
- White background for code presentation
- No table of contents

The final submission should follow the lecturer's assignment instructions and be submitted through Canvas.

---

# 16. Language Versions

- **English README:** `README.md`
- **中文 README:** [README_CN.md](README.zh-CN.md)

---

# 17. License

This repository is an academic assignment for COS30017.

It is intended for educational and assessment purposes.
