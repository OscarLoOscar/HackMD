Author: **Vincent Lau**
Note: This material is intended for educational purposes only. All rights reserved. Any unauthorized sharing or copying of this material, in any form, to any individual or party, for any use without prior permission, is strictly prohibited.
### Part 0: Prerequisites
0.1 Show hidden files & file extensions
- View -> "File name extensions" & "Hidden items", check both boxes.
- File name extensions are convenient for developers to handle & visualize code source files
- Lots of generated files/ config files are in hidden mode. We should visualize them for development.
![](https://hackmd.io/_uploads/Sk_henyt2.png)


### 0.2 Windows OS Requirement
- If your laptop's OS is not Windows 10 or above, please raise it to the trainer. Some of the installation guides may not be compatible, such as WSL.
- Ideally Random Access Memory (RAM) >= 16GB. If your laptop is running 8GB RAM, please raise to trainer as well.

### Part 1: JDK
![](https://hackmd.io/_uploads/HyE0g2JY3.png)
![](https://hackmd.io/_uploads/rJTRg2JF2.png)



- As a Java developer, you have to download JDK (Java Development Kit) for Java Application Development. We will further explore JDK/ JRE/ JVM later on. Let's start the installation first.
- Let's use JDK 17 (not 18), which is a LTS version (Long Term Support).
- If you have installed JDK before, but not version 17 or not in Linux env, please still proceed this section.
Based on your laptop specification, choose the corresponding JDK version to download.
 [Zulu Java 17 (WIndows OS)](https://www.azul.com/downloads/?version=java-17-lts&os=windows&package=jdk#zulu) Please check  64-bit or 32-bit.
![](https://hackmd.io/_uploads/ByPlz3yF2.png)



Place the unzipped package on your preferred path.
For example,==C:\software\zulu17.36.17-ca-jdk17.0.4.1-win_x64==
![](https://hackmd.io/_uploads/SJB-G3yFn.png)

- Setup %PATH% & %JAVA_HOME%
Go to "System enviroment variables" in the control panel ，（編輯系統環境變數）
![](https://hackmd.io/_uploads/HyJnG2JYh.png)

- Advanced -> Environment Variables
![](https://hackmd.io/_uploads/SJE2GnJF2.png)

- In System variables, select "Path", and then "Edit". 
![](https://hackmd.io/_uploads/SkRnMnyt3.png)

- Click "New", and place the JDK downloaded path as below.
![](https://hackmd.io/_uploads/SyXaMhyKn.png)

- Back to "System variables", "New" a new variable "JAVA_HOME", and place the JDK downloaded path (the path does not include "\bin").
![](https://hackmd.io/_uploads/r140z31Fh.png)

[result check]
- CMD to check if JDK is installed correctly
```
java --version
```
```
echo %JAVA_HOME%
```
```    
echo %PATH%
```
![](https://hackmd.io/_uploads/B1oZQn1F2.png)

- "javac" should show guidelines on how to use javac.
![](https://hackmd.io/_uploads/HJxMXh1K3.png)

### 3.2 Switch installed JDKs (Reference)
- You can install more than one JDK (Different JDK version/JDK provider)
- Redo Step 3.1 to reset JAVA_HOME & PATH environment variable to target JDK version.

### Part 2: Git
![](https://hackmd.io/_uploads/H1LfQh1Kh.png)

- DevOps tool used for source code management.
- Free and open-source version control system used to handle small to very large projects efficiently.
- Tracks changes in the source code, enabling multiple developers to work together on non-linear development.
### 4.1 Install Git
Offical git download
- For Windows, we download the standalone installer from official site
![](https://hackmd.io/_uploads/ByjMX3Jt3.png)
![](https://hackmd.io/_uploads/HJWmQ2yYh.png)

- Press "Next"
![](https://hackmd.io/_uploads/ByUm72kYn.png)

- Where to install git. You can choose your own path.
- For me, I had installed to ==D:\software\Git.==
![](https://hackmd.io/_uploads/BylNmnJYh.png)

- Choose components to install, simply just leave the default setting unchanged.
![](https://hackmd.io/_uploads/r1IrmnkKh.png)

- Default setting and Press Next
![](https://hackmd.io/_uploads/Sycr72JY3.png)

- Default setting and Press Next
![](https://hackmd.io/_uploads/BkJUQnJY3.png)

- Default setting and Press Next
![](https://hackmd.io/_uploads/B1rI7hkK2.png)

- Default setting and Press Next
![](https://hackmd.io/_uploads/HycIXnyK3.png)

- Default setting and Press Next
![](https://hackmd.io/_uploads/B1kPXnJKn.png)

- Default setting and Press Next
![](https://hackmd.io/_uploads/H1XvQnkKn.png)

- Default setting and Press Next
![](https://hackmd.io/_uploads/HyvPm3kKh.png)

- Default setting and Press Next
![](https://hackmd.io/_uploads/Sk3PX2kF2.png)

- Default setting and Press Next
![](https://hackmd.io/_uploads/HJx_721Yn.png)

- Configure experimental options. These two features are new and optional. I will suggest you check “Enable experimental built-in file system monitor“. Usage we will see later. This will be the last screen of setup and now click on Install.
![](https://hackmd.io/_uploads/SyL_7hJt3.png)

![](https://hackmd.io/_uploads/S1Ku7hyth.png)

![](https://hackmd.io/_uploads/H16uXnJK3.png)

- Environment variable (Setup %PATH%)
Go to "System enviroment variables" in the control panel
![](https://hackmd.io/_uploads/SJMYQ2yt2.png)

- Advanced -> Environment Variables
![](https://hackmd.io/_uploads/ryUKmnkK3.png)

- In System Variables, select "Path", and then "Edit". 
![](https://hackmd.io/_uploads/H19tX2yKn.png)

- Click "New", and place the git downloaded path as below.
![](https://hackmd.io/_uploads/HkgcQn1Fn.png)

- If you don't have WSL2/WSL, it is recommended to use git-bash as terminal (pin it to taskbar, easy to launch later)
![](https://hackmd.io/_uploads/B18qQ31t2.png)

[Result check]
- "where git" to check what git versions are installed. "git --version" to check what version of git is installed
```
# check git version
git --version
# where did you install the git
where git
```
![](https://hackmd.io/_uploads/S1ZnXnyYn.png)

### 4.2 Create Github account
![](https://hackmd.io/_uploads/SJDhmnJt2.png)

- As a developer, create a github account to start your journey.
- Create your own Github Account [ignore if you have created before].
- Update your github account info (https://hackmd.io/0L9QRERCSWSmeTEiIt4Q3w)
- It is a well known open source repository for sharing idea/ projects among the developers' community. You will find lots of useful projects/materials in github during your life as a developer. Over 80 million developers are using github as of 2022.
- You should store or backup your own projects/ material/ documents by github, so that you can refer to it in the future easily.
- Vincent's github profile - You can follow me (Star my repositories)
### 4.3 Setup SSH key
Generate ssh key - from github (Reference, or follow the steps below)
1. Open Git Bash
2. Generate ssh key
```
# Type this command to generate ssh key. The ssh key will be located in your laptop C:/Users/XXXX/.ssh
ssh-keygen -t ed25519 -C "your_email@example.com"
```
**[if fail in Step 2]** If you are using a legacy system that doesn't support the Ed25519 algorithm, use:
```
# only execute when you cannot success execute ED25519
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
3. ==**[Just Enter]**== You will find "Enter a file in which to save the key", please press Enter. This accepts the default file location.
```
# Sample
> Enter a file in which to save the key (/Users/you/.ssh/id_algorithm): [Press enter]
```
4. ==**[Just Enter]**== At the prompt, ask for a secure passphrase. Suggest pressing "enter" to skip.
 ```
 # Sample
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```
![](https://hackmd.io/_uploads/BkHr4h1F2.png)

**[result check]**
You will use the public key "id_ed25519.pub" later.
![](https://hackmd.io/_uploads/S1AvNhyYh.png)

### 4.4 Insert ssh key to Github a/c
1. Login your github a/c
2. Click the icon at the right top corner, Go to **Settings**.
![](https://hackmd.io/_uploads/BkzYE3kYn.png)

3. Go to **SSH and GPG keys**, and press **New SSH key**
![](https://hackmd.io/_uploads/B1Zq42yYh.png)

4. Open the **id_ed25519.pub** (public key) that we generated before, copy all contents of the key in the "Key" section shown below.  
  For title, simply put your email address.
![](https://hackmd.io/_uploads/Byxs42yF2.png)

[result check]
After adding the ssh key, you can download the github repository by git clone using SSH (You will use it in later installation part).
Now, you can download "repository" from github by using SSH, you will try later on.
![](https://hackmd.io/_uploads/Skd2V31F2.png)

### 4.5 Git config
```
# set your name when using git
git config --global user.name "your name"
# set your email address when using git
git config --global user.email your_email@example.com
# default branch name when using git (set to main)
git config --global init.defaultBranch main
# Set pager off for git branch
git config --global pager.branch false
# set pager off for git diff
git config --global pager.diff false
```
![](https://hackmd.io/_uploads/SJGCVnJt2.png)

![](https://hackmd.io/_uploads/rkDCE3kYn.png)

**[Result]** For Windows, the .gitconfig file is located C:\Users\yourname\
![](https://hackmd.io/_uploads/Hkz1Hn1th.png)

### Part 3: Maven
![](https://hackmd.io/_uploads/SJ1lrn1Y3.png)

- Project management and comprehension tool that provides developers a complete build lifecycle framework.
- Development teams can automate the project's "build" infrastructure in almost no time as Maven uses a standard directory layout and a default build lifecycle.
- You will learn and use it when developing a Java & Springboot application.
5.1 Install Maven 3
[Offical Maven Download](https://maven.apache.org/download.cgi) (as of 2023.06.30, should be version 3.9.3. For Maven, fine to get the latest version.
![](https://hackmd.io/_uploads/SyRTS2yY3.png)

- No installation process, extract the Maven archive to a directory of your choice once the download is complete. For example, C:\software\apache-maven-3.8.6
![](https://hackmd.io/_uploads/HyNCShJt2.png)

### 5.2 Add MAVEN_HOME System Variable
1. Open the Start menu and search for [environment variables](https://phoenixnap.com/kb/windows-set-environment-variable).
2. Click **Edit the system environment variables** result.
![](https://hackmd.io/_uploads/SyimI31Kn.png)

- Click the **New** button under the System variables section to add a new system environment variable.
![](https://hackmd.io/_uploads/BJKSU3yFh.png)

- Click the **New** button under the System variables section to add a new system environment variable.
![](https://hackmd.io/_uploads/Byz8Lhyt3.png)

- Enter **MAVEN_HOME** as the variable name and the path to the Maven directory as the variable value. Click **OK** to save the new system variable.
![](https://hackmd.io/_uploads/SJQwUnyF2.png)

![](https://hackmd.io/_uploads/HJdwIhyK3.png)

### 5.3 Add MAVEN_HOME to PATH Variable
- Select the **Path** variable under the System variables section in the Environment Variables window. Click the **Edit** button to edit the variable.
![](https://hackmd.io/_uploads/r1bK82kY2.png)

- Click the **New** button in the Edit environment variable window.
![](https://hackmd.io/_uploads/Bkw98n1Y2.png)

- Enter **%MAVEN_HOME%\bin** in the new field. Click **OK** to save changes to the **Path** variable.
![](https://hackmd.io/_uploads/rJCc8hyth.png)

- Click **OK** in the Environment Variables window to save the changes to the system variables
![](https://hackmd.io/_uploads/B1ShI2yY3.png)

[Result Check]
- Check maven version
  - "Java version" should be the current java version
  - "Runtime path" should be same as java_home
  - Maven home should be same as %MAVEN_HOME%
```
mvn -v
```
![](https://hackmd.io/_uploads/BJvTL2kt3.png)

- You may check %MAVEN_HOME% and %PATH% as well, which are just set by you.
![](https://hackmd.io/_uploads/Hk3pI2kFh.png)

### Part 4: Visual Studio Code
![](https://hackmd.io/_uploads/rkN083JKh.png)

- **We will use VSCode to code your Java & Springboot programs in the coming weeks!**
- Visual Studio Code is a lightweight but powerful source code editor which runs on your desktop and is available for Windows, macOS and Linux.
- If you have programming background and want to use "IntelliJ IDEA" instead of VSCode, it's fine, just an IDE. But I would still recommend you to try VSCode, and feel how lightweight it is.
6.1 Install VSCode from Official Site
- Install VScode in Windows OS directly, you can still use VSCode in Ubuntu Env.
[VScode Download](https://code.visualstudio.com/download) - Choose Windows, **Choose other system type if needed (64-bit / 32-bit)**
![](https://hackmd.io/_uploads/ryMGP31Yn.png)

- After downloading and unzipping, start the installation.
![](https://hackmd.io/_uploads/SJvGw2yK2.png)

![](https://hackmd.io/_uploads/Hyg7XpA_h.png)
![](https://hackmd.io/_uploads/ByxX7p0_3.png)
![](https://hackmd.io/_uploads/BJl7XT0u2.png)

### [Result Check]
- After reboot ,  you can see the path is updated.
- If not , set the VSCode installed path to $PATH (System Env Variable), so that you can use code . to launch VScode, no matter in Windows or Linux OS Env.
![](https://hackmd.io/_uploads/BkXFd3yt3.png)

Next time, you can simply type 
```"code ."```
to open VSCode app in a project folder.
![](https://hackmd.io/_uploads/BJRO_3yth.png)

### 6.2 Extensions
- Explorer / Search / Extensions are common functions in VScode. Put it in the menu bar on the left hand side of VSCode.
![](https://hackmd.io/_uploads/HkqmFhkYh.png)

- **Extensions** in VSCode help it become an integrated IDE with powerful functions, like color themes/ syntax management/ icon setting/ text color for different file types. All of those features enable you to code much more easily in VSCode.
![](https://hackmd.io/_uploads/r1gVY2yF3.png)

You can install all of the extensions below:
- ==Language Support for Java(TM) by Red Hat==
- ==Extension Pack for Java (Install this, the other 4 Java extensions will be installed automatically)==
- ==Maven for Java==
- ==Debugger for Java==
- ==Project Manager for Java==
- ==Test Runner for Java==
- ==Ayu - file/folder logo==
- ==One Dark Pro - themes (One Dark Pro Darker)==
- ==Spring Initializer Java Support==
- ==Spring Boot Tools==
- ==Spring Boot Dashboard==
- ==Lombok Annotations Support for VS Code==
- ==XML==
- ==YAML==
- ==SQL Beautify==
- ==Dependency Analytics==
- ==Markdown Preview Enhanced==
- ==Prettier - Code formatter==
### 6.3 Code Formatter/ settings.json/ key shortcut
#### Step 1: VSCode general setting - settings.json
- **In VSCode, press
```
shift+crtl+p
```
 type **"open settings json"** and select **"Open Settings(JSON)"**. 
- Overwrite your 
```
settings.json
```
by [settings.json](https://github.com/muecode/laptop-setup/blob/main/vscode/setting/settings.json) in github/muecode.
![](https://hackmd.io/_uploads/r1g8j31F3.png)

### [Result]
![](https://hackmd.io/_uploads/HyU8j3kY2.png)

### Step 2: VSCode Code Formatter - googlestyle.xml
CodeFormatter helps you auto-format your code to align the maven checkstyle/pmd plugin.
- From github laptop-setup, download the [googlestyle.xml](https://github.com/muecode/laptop-setup/blob/main/vscode/code-formatter/java/googlestyle.xml) into a local folder **[the following just a sample folder location]**
```
# For example, I download it to here.
C:\projects\github\laptop-setup\vscode\code-formatter\java\googlestyle.xml
```
![](https://hackmd.io/_uploads/r1ty33yFh.png)

- **In VSCode**,
```
shift+crtl+p
```
, type "open settings json" and select **"Open Settings(JSON)"**.
- Update the path value to **"java.format.settings.url"**
- ==For Windows, you have to use double slash \\ to represent the value of \ in json.==
```
C:\\projects\\github\\laptop-setup\\vscode\\code-formatter\\java\\googlestyle.xml
```
![](https://hackmd.io/_uploads/HJPQh21F2.png)

- Doublecheck **"lineSplit"** to **80** and **"comment.line_length"** to **200**.
![](https://hackmd.io/_uploads/HkCQhn1Fh.png)

#### Step 3: VSCode keyboard shortcut - keybindings.json
- **In VSCode**, 
```
shift+crtl+p
```
 type **"keyboard shortcuts json"** & select **"Open Keyboard Shortcut(JSON)"**
![](https://hackmd.io/_uploads/ByBqh3yKh.png)

- You can find the setup file for "Keyboard Shortcuts (JSON)" in github [keybindings.json](https://github.com/muecode/laptop-setup/blob/main/vscode/keyboard-shortcut/keybindings.json)
- Copy the file content to the above keybindings.json file.
  These are the shortcuts that you would frequently use:
  ```
  - shift+crtl+f: Auto format the code
  - shift+crtl+o: Organize java Imports, remove unused Imports
  - shift+crtl+k: Restart VSCode
  ```
### [Result]
- To let the above configurations take effect, you have to **restart the VSCode (you can just shift+crtl+k)**
![](https://hackmd.io/_uploads/HJbeThJK2.png)

**For windows , left hand side , press Search , input ctrl to replace cmd.**
You can use all the short cuts now.
![](https://hackmd.io/_uploads/rkie6nkKh.png)


