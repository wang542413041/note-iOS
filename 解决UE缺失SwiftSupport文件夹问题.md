1. 拷贝并解压原来的IPA文件

2. 提取解压缩包内的Frameworks内的Swift相关内容并拷贝至自创建的SwiftSupport文件夹内

3. 将原IPA内的Payload内容和新创建的SwiftSupport文件夹内容重新压缩为IPA
```
zip -r upload.ipa Payload SwiftSupport
```
