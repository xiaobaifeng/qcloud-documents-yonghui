云平台云服务器使用 KMS 方式对 Windows 服务器进行授权。
目前只有 Windows2008 和 Windows2012 需要做这种方式的授权。
## 激活前须知
1. Windows 上的 SPP Notification Service，是用来执行激活相关的服务，需要保证正常运行，如下图：  
![](//mccdn.qcloud.com/img56b1caa1eec42.png)  

2. 某些优化软件可能会禁用修改服务相关执行程序的执行权限，例如 sppsvc.exe 进程的执行权限若被修改，会导致服务运行不正常。  
![](http://mc.qcloudimg.com/static/img/685fe41ef992f11ba305dfb570cb916c/21.png)  

 在尝试激活 Windows 云服务器之前，请确保 Windows 上这个服务和其他基本功能正常。
 
## 自动激活
云平台为 Windows 服务器的激活封装了一个脚本，简化了手工激活的步骤。
请在您的 Windows 云服务器上访问以下地址：http://mirrors.tencentyun.com/install/windows/activate-win.bat 下载脚本，并在下载完成后执行该脚本，即可完成自动激活。

## 手工运行激活
激活步骤：
1. 登录您的云平台 Windows 云服务器。
2. 单击【开始】>【运行】，输入`cmd.exe`以打开控制台窗口。
3. 在控制台依次输入一下命令：
```
cscript /nologo %windir%/system32/slmgr.vbs -skms kms.tencentyun.com:1688
cscript /nologo %windir%/system32/slmgr.vbs -ato
```

实现以上步骤即可完成手工运行激活。

>**注意：**
> 在某些系统上，如果系统时钟存在问题，手工激活的时候会出现错误，此时需要先同步系统时钟。
> 同步时钟的方法为：在控制台窗口输入以下命令：
>```
>w32tm /config /syncfromflags:manual /manualpeerlist:"ntpupdate.tencentyun.com"
>w32tm /resync
>```



