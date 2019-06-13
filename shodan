原文链接：https://www.t00ls.net/thread-51462-1-1.html    
shodan针对每个icon都分配了一个hash。在shodan的搜索语法为:"http.favicon.hash:-1507567067"。看到了很多实用该icon的资产。

这个hash的计算是通过先对图标进行base64编码。并使用mmh3进行hash计算。    
那么我可以通过python脚本进行计算。（前提是需要安装pip install mmh3库）。接下来我们以dedecms为例。    
py代码如下:    
```
import sys
import requests
import mmh3


url=sys.argv[1]


response = requests.get('{}'.format(url))

favicon = response.content.encode('base64')

hash = mmh3.hash(favicon)

print hash

```

运行代码 python 1.py http://www.xxx.com/favicon.ico 得到结果为:-47597126    
在shodan上使用语法搜索: http.favicon.hash:-47597126
