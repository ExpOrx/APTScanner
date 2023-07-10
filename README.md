# APTScanner

## How to use?
```
#!/usr/bin/env python
# -*- coding: utf-8 -*-
# @Time : 7/10/2023 3:35 PM
# @Author : 2ero
# @File : APTScanner.py
# @Software: PyCharm
import hashlib
import requests
IP=""
PORT=""
def main():
    url = 'http://IP:PORT/'
    PATH = "" #your file path
    files = {'file': open(PATH, 'rb')}

    with open(PATH, 'rb') as fp:
        data = fp.read()
    file_md5 = hashlib.md5(data).hexdigest()
    r = requests.post(url, files=files)
    if r.status_code==200:
        report_url = "http://IP:PORT/sample/%s"%file_md5
        print(report_url)
if __name__ == '__main__':
    main()
```
