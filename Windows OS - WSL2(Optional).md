Author: [Vincent Lau](https://www.linkedin.com/in/vincent-lau-30435bb6/)
Note: This material is intended for educational purposes only. All rights reserved. Any unauthorized sharing or copying of this material, in any form, to any individual or party, for any use without prior permission, is strictly prohibited.

Reference: https://learn.microsoft.com/en-us/windows/wsl/install

### Prerequisites
Windows OS Version: 
- Windows 10 version 2004 and higher (Build 19041 and higher) or Windows 11,
  - Go to Part 1a
- If you are on earlier versions,
  - Go to Part 1b
  - 
### Part 1a: WSL2 - Ubuntu
![](https://hackmd.io/_uploads/BkXgJklF3.png)

Developers can access the power of both Windows and Linux at the same time on a Windows machine. The ==Windows Subsystem for Linux== (WSL) lets developers install a Linux distribution (such as Ubuntu, OpenSUSE, Kali, Debian, Arch Linux, etc) and use Linux applications, utilities, and Bash command-line tools directly on Windows, unmodified, without the overhead of a traditional virtual machine or dualboot setup.

Reference: https://learn.microsoft.com/en-us/windows/wsl/install

You can now install everything you need to run WSL with a single command. 
- Open PowerShell or Windows Command Prompt in administrator mode by right-clicking and selecting "Run as administrator"
- Enter the ==wsl --install== command
- Restart your machine.
```
wsl --install
```
#### [result check] 
- In Windows Terminal (cmd/ powershell), type the following command to check wsl version.
```
wsl -l -v
```
![](https://hackmd.io/_uploads/HkPm1keK2.png)

- Work normally after installation. You should be able to mount the Windows drive from WSL2 Environment by/mnt/c (= Windows C drive) in Linux env.
![](https://hackmd.io/_uploads/Bk37y1xFn.png)

### Part 1b: WSL2/ WSL - Ubuntu
Reference: https://learn.microsoft.com/en-us/windows/wsl/install-manual
Step 1: Enable the Windows Subsystem for Linux
- Find Windows PowerShell, and run as administrator.
![](https://hackmd.io/_uploads/ryWU-klF2.png)


- Enter the following command to enable and enter "y" to restart your computer.
```
# Enable windows-subsystem-linux
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all
```
![](https://hackmd.io/_uploads/S1d4bylFn.png)
- **We recommend** moving on to step 2 to install WSL2 if your laptop has the following requirements:
  - x64 system: OS Version 1903 or later, with build 18362 or later
  - arm64: Version 2004 or later, with Build 19041 or later
- Otherwise, If you can only install WSL 1 (WSL), please execute the command and restart, then jump to Step 5.

#### Step 2: Enable Virtual Machine feature
Before installing WSL 2, you must enable the Virtual Machine Platform optional feature. Your machine will require [virtualization capabilities](https://learn.microsoft.com/en-us/windows/wsl/troubleshooting#error-0x80370102-the-virtual-machine-could-not-be-started-because-a-required-feature-is-not-installed) to use this feature.
Run the following command in Windows PowerShell: 
```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all
```
#### Step 3: Download the Linux kernel update package
[WSL2 Linux kernel update package (x64 machine)](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)
Note:
- If you're using an ARM64 machine, please download the [ARM64 package](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_arm64.msi) instead. 
- If you're not sure what kind of machine you have, open Command Prompt or PowerShell and enter: ==systeminfo | find "System Type"==
- Double-click to run - you will be prompted for elevated permissions, select ‘yes’ to approve this installation.
![](https://hackmd.io/_uploads/SJbUz1lFn.png)

#### Step 4 - Set WSL2 as your default version
- Open PowerShell
- Run this command to set WSL 2 as the default version before installing a linux distribution
```
wsl --set-default-version 2
```
![](https://hackmd.io/_uploads/r1zwfJlKn.png)

#### Step 5 - Install your Linux distribution of choice
- Open the [Microsoft Store](https://aka.ms/wslstore) and select your favorite Linux distribution. You can search "linux" in Microsoft Store and download Ubuntu.
![](https://hackmd.io/_uploads/BymuGyetn.png)

- If the installation has the following error, please re-do step 3 to install the update package again. And re-launch ubuntu.
```
0x800701bc WSL 2 requires an update to its kernel component. XXXX...restart...
```
If installation succeeds, you will find the screen below and follow the steps to complete the installation.
![](https://hackmd.io/_uploads/SJAtMJgF2.png)

![](https://hackmd.io/_uploads/HyXczkgtn.png)

For others, please press enter to proceed. (select drive & folder in windows for /mnt/ as mount drive)
![](https://hackmd.io/_uploads/SkP5fkeKh.png)

![](https://hackmd.io/_uploads/B1oqM1eYh.png)

#### [result check] 
- In Windows Terminal (cmd/ powershell), type the following command to check wsl version.
```
wsl -l -v
```
![](https://hackmd.io/_uploads/HyijGJgY2.png)

- Work normally after installation. You should be able to mount the Windows drive from WSL2 Environment by==/mnt/c== (= Windows C drive) in Linux env.
![](https://hackmd.io/_uploads/H1enz1lYh.png)


### Part 2: zsh, Oh-my-zsh & Power10k
![](https://hackmd.io/_uploads/rkZazyxF3.png)

- [ZSH](https://github.com/robbyrussell/oh-my-zsh/wiki/Installing-ZSH), called the Z shell, is an extended version of the Bourne Shell (sh)
- It’s based on the same shell as Bash, ZSH has many of the same features, which is easy for everyone to switch over.
Some features of ZSH, but not limited to:
- Automatic cd: Just type the name of the directory
- Recursive path expansion: For example “/u/lo/b” expands to “/usr/local/bin”
#### 2.1 Windows Terminal
- Download "Windows Terminal" from Microsoft Store
![](https://hackmd.io/_uploads/HylW1QJxYn.png)

- Open "Windows Terminal", Windows PowerShell is set as default.
![](https://hackmd.io/_uploads/H1w1Qygt2.png)

- Set Ubuntu as default in "Startup"
![](https://hackmd.io/_uploads/Sko1QylY3.png)

#### 2.2 Install zsh/ git/ curl/ wget
- Make sure curl/ wget/ git is in place (We use git to download oh-my-zsh)
```
sudo apt install curl wget git
```
![](https://hackmd.io/_uploads/HyDlQJgK2.png)

- Install zsh
```
sudo apt install zsh
```
![](https://hackmd.io/_uploads/BktbXyeY2.png)

#### 2.3 Install oh-my-zsh
```
sh -c "$(curl -fsSL 
https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
- ==Enter Y if asks for setting zsh as default shell==
![](https://hackmd.io/_uploads/Hy_XQJeth.png)

- After installation completed,==echo $SHELL==, it should return "/usr/bin/zsh"
![](https://hackmd.io/_uploads/rJVNmylKh.png)

### [Result Check]
"oh-my-zsh" should be already installed in ==/home/username/.oh-my-zsh==
i.e.==ls -a== will list all files under the current folder, including the hidden files.
![](https://hackmd.io/_uploads/H1CrQ1xth.png)

#### 2.4 Install New Font
In order to show some icons and texts correctly, we have to install some new fonts under linux.
- [MesloLGS NF Regular.ttf](https://github.com/romkatv/dotfiles-public/raw/master/.local/share/fonts/NerdFonts/MesloLGS%20NF%20Regular.ttf)
- [MesloLGS NF Bold.ttf](https://github.com/romkatv/dotfiles-public/raw/master/.local/share/fonts/NerdFonts/MesloLGS%20NF%20Bold.ttf)
- [MesloLGS NF Italic.ttf](https://github.com/romkatv/dotfiles-public/raw/master/.local/share/fonts/NerdFonts/MesloLGS%20NF%20Italic.ttf)
- [MesloLGS NF Bold Italic.ttf](https://github.com/romkatv/dotfiles-public/raw/master/.local/share/fonts/NerdFonts/MesloLGS%20NF%20Bold%20Italic.ttf)
---
- Double click each ttf file to open it up and then press "install" button for installation. (4 ttf files in total)
![](https://hackmd.io/_uploads/S1Ky4yeF2.png)

- Back to "Windows Terminal", go to "Setting" -> "Ubuntu" on left hand side menu -> "Additional settings" -> Appearance
![](https://hackmd.io/_uploads/rJpyE1gt2.png)


- Select **"MesloLGS NF"** in "Font face"
- You can select your favourite "Color scheme" and "Font size" as well.
![](https://hackmd.io/_uploads/Bypx4yxK3.png)

### 2.5 Install Powerlevel10k
```
git clone https://github.com/romkatv/powerlevel10k.git $ZSH_CUSTOM/themes/powerlevel10k
```
#### Install zsh-autosuggestions & zsh-syntax-highlighting
```git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
```
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```
![](https://hackmd.io/_uploads/S1kQEkxth.png)

#### [Result Check]
The theme "powerlevel10k" is installed in ==/home/xxx/.oh-my-zsh/custom/themes==
![](https://hackmd.io/_uploads/rkVEE1xYn.png)

### 2.6 Configure powerlevel10k
- Use nano command to open .zshrc
```
nano ~/.zshrc
```
![](https://hackmd.io/_uploads/HywSNkgY3.png)


- Revise ZSH_THEME to ==powerlevel10k/powerlevel10k==
- Revise plugins ==plugins=(git zsh-autosuggestions zsh-syntax-highlighting)==
i.e. To exit, Enter Ctrl + x; then after you made changes in the file, it will ask you if you want to save, Y and Enter.
![](https://hackmd.io/_uploads/SkcU4yxF3.png)

![](https://hackmd.io/_uploads/S1RUN1gYn.png)

- Run ==source ~/.zshrc== to restart SHELL so that the theme can be refreshed.
![](https://hackmd.io/_uploads/rJDDVJeKh.png)

#### 2.7 Your own theme style
- Exit and reopen the terminal, the configuration interface will be shown.
(If the configuration interface cannot be triggered, you can use command p10k configure.
Now, it is your turn to set up your favourite style.
![](https://hackmd.io/_uploads/H1FQB1gFh.png)

If you see this page, please just type "y" to install the font.
![](https://hackmd.io/_uploads/ByZNSJeY2.png)

Type "y" if you can see the icon normally:
![](https://hackmd.io/_uploads/Byj4B1xKh.png)

Type "y" if there is no overlap for icons.
![](https://hackmd.io/_uploads/SJMvrylFh.png)

Your choice here.
![](https://hackmd.io/_uploads/SJdDByeY3.png)

- **Please choose ==Unicode== to display those special icons in prompt corrently.**
![](https://hackmd.io/_uploads/B10PrJlY3.png)

- Show current time & time format
![](https://hackmd.io/_uploads/BJ6Or1etn.png)

- Prompt 內的分隔符號、末端的形狀
![](https://hackmd.io/_uploads/HJ4YS1eFn.png)

![](https://hackmd.io/_uploads/S1cFr1etn.png)

- 要像傳統 Prompt 和指令在同一行，或分成兩行
![](https://hackmd.io/_uploads/HyJcHJeth.png)

- 如果是分成兩行，可以幫第一行左右 Prompt 加連接線
![](https://hackmd.io/_uploads/By4cB1ltn.png)

- 如果是分成兩行，可以為末端設定 Frame 風格，多一個圓弧線條
![](https://hackmd.io/_uploads/B1c9SyxF3.png)

- 設定兩次指令之間的 Prompt 空間
![](https://hackmd.io/_uploads/HyA5SyxF3.png)

- 會讓 Prompt 看起來更符合閱讀的語意，例如「on」某個 branch、「took」幾秒。不過 Terminal 用久了其實都很清楚每個資訊代表的意思，所以我比較喜歡 (1) Concise 簡潔一點
![](https://hackmd.io/_uploads/HyEoSyxK3.png)

![](https://hackmd.io/_uploads/HJdiHJlYn.png)

- **[Optional, you can skip this]** Set something special for your own prompt
```
nano ~/.p10k.zsh
```
[Find your favourite icon](https://www.nerdfonts.com/cheat-sheet) -> Nerd Font Cheat Sheet
![](https://hackmd.io/_uploads/SJUkLyxK3.png)

Secondly, you can set battery & ram & cpu [Many others, you can try yourself].
Find POWERLEVEL9K_RIGHT_PROMPT_ELEMENTS and uncomment battery & ram & load
![](https://hackmd.io/_uploads/SJewZLygtn.png)

![](https://hackmd.io/_uploads/r17ZLkxYh.png)

### [result check]
![](https://hackmd.io/_uploads/r1WMIJeK3.png)


### Part 3: JDK in WSL2
![](https://hackmd.io/_uploads/H1uz8ygFh.png)

![](https://hackmd.io/_uploads/r1oz8JlKn.png)


- As a Java developer, you have to download JDK (Java Development Kit) for Java Application Development. We will further explore JDK/ JRE/ JVM later on. Let's start the installation first.
- Let's use JDK 17 (not 18), which is a LTS version (Long Term Support).
- **If you have installed JDK before, but not version 17 or not in Linux env, please still proceed this section.**
#### 3.1 Install Zulu JDK17
#### Step 1: Download Zulu JDK 17
- Back home directly (By cd ~), use wget to download zulu17 JDK from [azul.com/downloads ](azul.com/downloads)
- The downloaded files tar.gz will be located in the home directory
```
wget https://cdn.azul.com/zulu/bin/zulu17.36.17-ca-jdk17.0.4.1-linux_x64.tar.gz
```
![](https://hackmd.io/_uploads/Bk9PKyltn.png)

#### Step 2: Unzip the tar.gz file
```
tar -zxvf zulu17.36.17-ca-jdk17.0.4.1-linux_x64.tar.gz
```
![](https://hackmd.io/_uploads/S1_uYklY3.png)

[result] - The unzipped folder is in the home directory
![](https://hackmd.io/_uploads/HkCdtJgth.png)

#### Step 3: Move the files
- Move the files from the unzipped folder to /usr/local/java
```
sudo mv zulu17.36.17-ca-jdk17.0.4.1-linux_x64 /usr/local/java
```
![](https://hackmd.io/_uploads/ByiYK1gth.png)

#### Step 4: Setup $JAVA_HOME & $PATH
```
nano .zshrc
```
In .zshrc, assign the following variables
![](https://hackmd.io/_uploads/HyD9FJeY2.png)

### [Result] - Important Step
- Able to return $JAVA_HOME & Java Version by the following commands
```
# Check $JAVA_HOME
echo $JAVA_HOME
# Java Version
java --version
# Check Path variable, so that it can locate java correctly
echo $PATH
```
![](https://hackmd.io/_uploads/HyLoFJgY3.png)

![](https://hackmd.io/_uploads/HJ9jtkgFh.png)

#### 3.2 Switch installed JDKs (Reference)
- You can install more than one JDK (Different JDK version/JDK provider)
- Redo Step 3.1 to reset JAVA_HOME & PATH environment variable to target JDK version.

### Part 4: Git in WSL2
![](https://hackmd.io/_uploads/B1H3tyxK2.png)

- DevOps tool used for source code management.
- Free and open-source version control system used to handle small to very large projects efficiently.
- Tracks changes in the source code, enabling multiple developers to work together on non-linear development.
#### 4.1 Install Git
- Add the repositories by using the following command.
```
sudo add-apt-repository ppa:git-core/ppa
```
- Update the Linux system using the given command 
```
sudo apt-get update -y
```
- Now we use the following command to install the Git package in WSL.
```
sudo apt-get install git
```
- Check git version
```
#To check it by git command. The git version will be returned.
git --version
# where git, where are all the git located.
where git
# which git, which git is currently using
which git
```
![](https://hackmd.io/_uploads/BkyRKyeF2.png)

### 4.2 Create Github account
![](https://hackmd.io/_uploads/B1NRKJet3.png)

- As a developer, create a github account to start your journey - https://github.com/
- It is a well known open source repository for sharing idea/ projects among the developers' community. You will find lots of useful projects/materials in github during your life as a developer. Over 80 million developers are using github as of 2022.
- You can store or backup your own projects/ material/ documents by github, so that you can refer to it in the future easily.
#### 4.3 Setup SSH key
[Generate ssh key - from github](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent)
1. Open Terminal
2. Generate ssh 
```
# Type this command to generate ssh key in your laptop ~/.ssh
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
3. Prompted to "Enter a file in which to save the key," press Enter. This accepts the default file location.
```
# Sample
> Enter a file in which to save the key (/Users/you/.ssh/id_algorithm): [Press enter]
```
4. At the prompt, ask for a secure passphrase. Suggest to press "enter" to skip.
```# Sample
> Enter passphrase (empty for no passphrase): [Type a passphrase]
> Enter same passphrase again: [Type passphrase again]
```
### [result]
![](https://hackmd.io/_uploads/S1zFoklKh.png)

### 4.4 Insert ssh key to Github a/c
1. Login your github a/c
2. Go to "Settings"
![](https://hackmd.io/_uploads/S1xqikgY2.png)

3. Go to "SSH and GPG keys", and then "New SSH key"
![](https://hackmd.io/_uploads/S149o1lth.png)

4. Find the generated ssh public key (id_rsa.pub) in .ssh folder.
```
# Go to .ssh folder and print the key content in console
cat id_rsa.pub
```
![](https://hackmd.io/_uploads/ryhooJetn.png)

- Place the whole content of id_rsa.pub (public key) in the "Key" section as below. For title, simply put your email address.
![](https://hackmd.io/_uploads/ryD6j1xF3.png)

### [Result check]
The SSH key is associated with my github account (SSH key pair represents the relationship between the github account and the laptop).
After adding the ssh key, you can download the github repository by ==git clone== using ==SSH== (You will use it in later installation part).
Now, you can download "repository" from github by using ==SSH== .You will try later on.
![](https://hackmd.io/_uploads/HJ-JhylF3.png)


### Part 5: Maven in WSL2
![](https://hackmd.io/_uploads/S1Ik3kgt2.png)

- Project management and comprehension tool that provides developers a complete build lifecycle framework.
- Development teams can automate the project's "build" infrastructure in almost no time as Maven uses a standard directory layout and a default build lifecycle.
- You will learn and use it when developing a Java & Springboot application.
### 5.1 Install Maven 3
#### Step 1: Download Maven 3
- Back home directly (By cd ~), use wget to download maven 3 from apache.org
- The downloaded files tar.gz will be located in the home directory
```
wget https://dlcdn.apache.org/maven/maven-3/3.8.6/binaries/apache-maven-3.8.6-bin.tar.gz
```
![](https://hackmd.io/_uploads/ryXWnyeY2.png)

Step 2: Unzip the tar.gz file
tar -zxvf apache-maven-3.8.6-bin.tar.gz
![](https://hackmd.io/_uploads/H13ZhkeF2.png)

#### [result] - The unzipped folder is in the home directory
![](https://hackmd.io/_uploads/rJUmhkxKh.png)

#### Step 3: Move the files
- Move the files from the unzipped folder to /usr/local/maven
```
sudo mv apache-maven-3.8.6 /usr/local/maven
```
![](https://hackmd.io/_uploads/SkqV31xYh.png)

#### Step 4: Setup $M2_HOME / &MAVEN_HOME / $PATH
```
nano .zshrc
```
In .zshrc, export MAVEN_HOME, so that the terminal startup can locate the maven directory for mvn. 
![](https://hackmd.io/_uploads/SkvSh1eYn.png)

### [Result] - Important
- Able to return $MAVEN_HOME & maven Version by the following commands
```
# Check $MAVEN_HOME
echo $MAVEN_HOME
echo $M2_HOME
# check maven version currently using
mvn -v
# Check Path variable, so that OS can locate maven correctly
echo $PATH
```
![](https://hackmd.io/_uploads/B1DU3kxF2.png)

