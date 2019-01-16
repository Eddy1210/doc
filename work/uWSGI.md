- WSGI是一种通信协议。
- uwsgi同WSGI一样是一种通信协议。
- 而uWSGI是实现了uwsgi和WSGI两种协议的Web服务器。
```
uwsgi协议是一个uWSGI服务器自有的协议，据说该协议大约是fcgi协议的10倍那么快。它用于定义传输信息的类型（type of information），每一个uwsgi packet前4byte为传输信息类型描述，它与WSGI相比是两样东西。
```

[链接](https://henulwj.github.io/2016/04/20/uwsgi-common-use-parameters/)
