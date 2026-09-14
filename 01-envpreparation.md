# WSL2+Ubuntu环境  
## 之前安装DockerDesk时安装了WSL2，并且成功安装到D盘
截图表示系统里安装了一个名为 docker-desktop 的 WSL 发行版  

<div align="center">
  <img 
    src="{{ '/picture/1.png' | relative_url }}" 
    alt="docker-desktop" 
    width="700"
    height="500">
</div>
'wsl -l -v '  
列出当前系统中安装的所有 WSL（Windows Subsystem for Linux）发行版及其运行状态和版 本。
Ubuntu：是一个完整的操作系统（OS），包含内核、文件系统、桌面环境（可选）等。  
Docker：是一个容器化平台。它允许你把应用及其依赖打包成一个标准化的“容器”，这个容器可以运行在任何支持 Docker 的 Linux 系统上（包括 Ubuntu、CentOS、Debian 等）。  
# Ubuntu下载  
Ubuntu官网下载 WSL 分类下的 Get Ubuntu on WSL → Intel or AMD 64-bit architecture    
## 1. 停止系统  
wsl --terminate Ubuntu-22.04  

## 2. 导出系统到 D 盘（文件名假设为 ubuntu_backup.tar）  
wsl --export Ubuntu-22.04 D:\ubuntu_backup.tar  

## 3. 注销 C 盘上的原系统  
wsl --unregister Ubuntu-22.04  
  
## 4. 导入到 D 盘的 WSL 目录下
wsl --import Ubuntu-22.04 D:\WSL\Ubuntu2204 D:\ubuntu_backup.tar  

## 5. 删除临时备份文件（可选）  
del D:\ubuntu_backup.tar   
结果展示  
<div align="center">
  <img 
    src="{{ '/picture/2.png' | relative_url }}" 
    alt="ubuntu" 
    width="700"
    height="500">
</div>

## 目前我的powershell输入wsl默认启动的是LAPTOP-4LRGFQCE:/mnt/host/c/Users/yourname# 也就是就是进入安装的docker-desktop
输出wsl -d Ubuntu-26.04进入myra@LAPTOP...:~$ 进入安装的ubuntu      
在ubtuntu下执行命令    
'curl -LsSf https://astral.sh/uv/install.sh | sh'    
命令执行失败    
pip命令也不行 sudo命令也不行    
最终从github上面找到下载链接    
'cd /mnt/d/uv'    
把 uv 主程序移动到系统全局路径（这样在任何地方都能用    
'sudo mv uv-x86_64-unknown-linux-gnu/uv /usr/local/bin/'    
'uv --version'    
myra@LAPTOP-4LRGFQCE:/mnt/d/uv$ uv --version    
uv 0.12.13 (x86_64-unknown-linux-gnu)    
之后uv tool install --upgrade agentseek    
好慢啊！！！！！！！！！  ！！！！！！！！！    




