# Python KMS Server and Client

[![License](https://img.shields.io/badge/license-unlicense-lightgray.svg)](https://github.com/yanranxiaoxi/PYKMS/blob/master/LICENSE)

## 特性

* 回应 V4，V5 和 V6 KMS 的请求

* 支持激活 Windows 7 / 8 / 8.1 / 10、Windows Server 2008 R2 / 2012 / 2012 R2 / 2016、Office 2010 / 2013 / 2016

* 使用 Python 运行

## 环境要求

* Linux System

* Touchable Port 1688 or Other

* Python 2.6.x or Python 2.7.x with the `argparse` Module Installed

* Micropython Needs `libpcre` and `libffi`, and Modules in `micropythonlib`

## 安装说明

1. 安装 python-argparse 依赖

```
yum install python-argparse
```

2. 克隆代码

```
git clone https://github.com/yanranxiaoxi/PYKMS
```

3. 测试激活服务器

```
cd PYKMS
python server.py
```

4. 自动运行配置

   1. 拷贝 PYKMS 文件夹到 /usr/local/ 目录下

   ```
   cp -r py-kms /usr/local/
   ```

   2. 安装 supervisor

   ```
   yum install python-setuptools && easy_install supervisor && echo_supervisord_conf > /etc/supervisord.conf && easy_install supervisor
   ```

   3. 编写 supervisor 脚本，添加到 /etc/supervisord.conf 文件最后

   ```
   [program:pykms]
   command=python /usr/local/PYKMS/server.py
   user=root
   autostart=true
   autorestart=true
   ```

   4. 以 daemon 方式运行 supervisor

   ```
   supervisord
   ```

5. 客户端测试

   * 客户端下载 PYKMS 后，cd 到 PYKMS 目录，并执行

   ```
   python client.py -v [server_address]
   ```

   * 结果如下说明安装成功

   ```
   Connecting to [server_address] on port 1688...
   Connection successful!
   Sending RPC bind request...
   RPC bind acknowledged.
   ```

## 其他

   * [激活 Windows 系统](https://github.com/yanranxiaoxi/PYKMS/blob/master/README-windows.md)

   * [激活 Office 套件](https://github.com/yanranxiaoxi/PYKMS/blob/master/README-office.md)

### 更改监控地址和端口

* 支持使用如下方式运行激活服务器

* 默认 `[listen_address]` 为 `0.0.0.0`，默认 `[port]` 为 `1688`

```
python server.py [listen_address] [port]
```

* 支持使用如下方式测试激活服务器

* 默认 `[port]` 为 `1688`

```
python client.py [server_address] [port]
```

### 在 IPv6 上运行

* 要在 IPv6 上运行，请使用一个有效的 IPv6 地址，比如使用 `::`，作为 `[listen_address]`

## Micropython 支持（unix port only）

* 必须使用 Micropython v1.9 以上版本，因为对于 large int 的支持从该版本开始

* 你需要 `libpcre` 与 `libffi`

* 你需要一些标准的模块库

   ```
   micropython -m upip install -r requirements-micropython.txt
   ```

* 仅支持 unix 端口，其他平台缺少部分 stdlib，而且性能可能会存在问题
