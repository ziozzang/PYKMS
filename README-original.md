# History
py-kms is a port of node-kms by [markedsword](http://forums.mydigitallife.info/members/183074-markedsword), which is a port of either the C#, C++, or .NET implementations of KMSEmulator, of which the original version was written by [CODYQX4](http://forums.mydigitallife.info/members/89933-CODYQX4) and is derived from the reverse-engineered code of Microsoft's official KMS.

# Features
- Responds to V4, V5, and V6 KMS requests.
- Supports activating Windows 7/8/8.1/10/2008R2/2012/2012R2/2016 and Office 2010/2013/2016.
- It's written in Python.

# Dependencies
- Python 2.6 or higher, micropython v1.9 or higher.
- Python 2.6 needs the "argparse" module installed.
- Micropython needs libpcre and libffi, and modules in micropythonlib, check section below.

# Usage
- To start the server, execute `python server.py [listen_address] [port]`. The default listening address is `0.0.0.0` (all interfaces) and the default port is `1688`.
- To run the client, use `python client.py server_address [port]`. The default port is `1688`.
- To run on ipv6, please use a valid ipv6 address, for example `::` for broadcast.

# Micropython support (unix port only)
- Micropython v1.9 is necessary since large int support starts here.
- You need libpcre and libffi.
- You need some standard library of module. Use `micropython -m upip install -r requirements-micropython.txt` to install.
- Only unix port is supported. Other platforms don't have some stdlib and performance may be a problem. 
