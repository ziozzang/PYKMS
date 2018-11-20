## 激活 Office 套件

1. 确定自己安装的未激活 Office 为 VOL 版

2. 以管理员权限运行 cmd 或 Windows PowerShell

3. 执行以下指令

   ```
   cd %ProgramFiles%\Microsoft Office\[office_folder]
   cscript ospp.vbs /sethst:[server_address]:[port]
   cscript ospp.vbs /act
   cscript ospp.vbs /dstatus
   cscript ospp.vbs /remhst
   ```

   * 默认 `[port]` 为 `1688`

   * 当前支持的 `[office_folder]` 如下

      * Office 2016 为 `Office16`

	  * Office 2013 为 `Office15`

	  * Office 2010 为 `Office14`
