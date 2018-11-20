## 激活 Windows 系统

1. 以管理员权限运行 cmd 或 Windows PowerShell

2. 执行以下指令

   ```
   slmgr.vbs -upk
   slmgr.vbs -ipk [XXXXX-XXXXX-XXXXX-XXXXX-XXXXX]
   slmgr.vbs -skms [server_address]:[port]
   slmgr.vbs -ato
   ```

   * 请前往 [Microsoft Tech](https://technet.microsoft.com/en-us/library/jj612867.aspx) 获取 [XXXXX-XXXXX-XXXXX-XXXXX-XXXXX]

3. 验证激活

   ```
   slmgr.vbs -dlv
   ```
