在开发过程中，http(s)可以帮我们做很多事，比如获取图片、下载文件、请求数据等等可以说是非常方便。但是如果你认真观察过你就会发现，当你访问只支持http的网站时，浏览器会警告我们这个连接不安全，同样当你在高版本的Android或者iOS系统中使用http时,也会收到一些警告或者错误，它们都会建议你使用经过SSL加密后的https而非不加密的http。

Android
Android从9.0/P开始，处于安全性考虑默认不允许使用http请求了，所以如果打包时你选择的Target API Level大于27(不包括27)并且没有配置是否允许使用http请求，就会抛出异常：W/System.err: java.io.IOException: Cleartext HTTP traffic to ** not permitted。当然你可以通过配置AndroidMainfest.xml文件，在application标签下新增android:usesCleartextTraffic=”true”，或者降低Target API Level来继续使用http。

iPhone
在iPhone上，当你在Xcode上运行你的程序，第一次进行http请求时，会收到这样的警告：You are using download over http. Currently Unity adds NSAllowsArbitraryLoads to Info.plist to simplify transition, but it will be removed soon. Please consider updating to https，就是说你仍可以将NSAppTransportSecurity添加到info.plist中来使用http，但这将是将来删除。建议您从现在开始使用https连接。

总结
也就是说项目当中能使用https尽量使用https，至少在我们可以选择的时候，一定要选择https。
