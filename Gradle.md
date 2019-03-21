# Gradle 镜像

> https://www.zhihu.com/question/37810416/answer/73703268

使用阿里云的国内镜像仓库地址，就可以快速的下载需要的文件

修改项目根目录下的文件 build.gradle ：

```
buildscript {
    repositories {
        maven{ url 'http://maven.aliyun.com/nexus/content/groups/public/'}
    }
}

allprojects {
    repositories {
        maven{ url 'http://maven.aliyun.com/nexus/content/groups/public/'}
    }
}

```

然后选择重新构建项目就可以了

https://www.zhihu.com/question/37810416/answer/73703268



# Gradle Wrapper

[The Gradle Wrapper - Gradle User Guide Version 3.5](https://docs.gradle.org/current/userguide/gradle_wrapper.html)



使用 `./gradlew.bat` 或者 `./gradlew` 命令时，Gradle Wrapper 从 Gradle Repository下载 Gradle 软件包的时候很慢，原因是国内无法访问或者访问 Gradle 网站很慢。

解决办法：

首先电脑上有一个最新版本的 Gradle，并且`gradle`命令可以在命令行中使用：

- 在一个空目录中，使用 `gradle wrapper --gradle-version 3.5 `命令生成一个新的 Gradle Wrapper 包，命令将生成如下文件和目录：
  - gradle 目录：
    - gradle-wrapper.jar
    - gradle-wrapper.properties
  - gradlew 脚本（UNIX）
  - gradlew.bat 脚本（Windows）



然后，打开 gradle-wrapper.properties 文件， 复制 `distributionUrl` 的值，使用翻墙的浏览器下载 https://services.gradle.org/distributions/gradle-3.5-all.zip 文件并放在 D:\tools\gradle-3.5-all.zip。



使用 HTTP 服务器xxxx

```
#Wed Apr 19 10:53:02 CST 2017
distributionBase=GRADLE_USER_HOME
distributionPath=wrapper/dists
zipStoreBase=GRADLE_USER_HOME
zipStorePath=wrapper/dists
#distributionUrl=https\://services.gradle.org/distributions/gradle-3.5-all.zip
distributionUrl=http\://localhost:8080/gradle-3.5-all.zip
```

最后

## 使用

不要用Android Studio下载gradle，无论如何都不走代理，看见它在下载就马上强行杀进程，因为关不掉的，然后用命令行指定代理，

	./gradlew -DsocksProxyHost=127.0.0.1 -DsocksProxyPort=1080 tasks

只要第一次加入这个参数下载zip包，以后就会读取gradle.properties,也可以直接把这个参数加到环境变量GRADLE_OPTS里，再用

	./gradlew，export GRADLE_OPTS='-DsocksProxyHost=127.0.0.1 -DsocksProxyPort=1080'

在properties里设置的代理在下载依赖时有用，但是下载gradle本身时不生效，然而，无论怎么设置，AndroidStudio也不会走代理下载gradle,包括AS设置里指定的gradle jvm opts，至于下载依赖，包太小看不出来，但properties里的设置应该是有效的，

> 作者：啊鱼
> 链接：https://www.zhihu.com/question/37810416/answer/156162582
> 来源：知乎
> 著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。