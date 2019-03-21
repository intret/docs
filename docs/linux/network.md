# Linux 网络管理

## 获取公网IP地址


```shell
curl icanhazip.com
curl ifconfig.me
curl curlmyip.com
curl ip.appspot.com
curl ipinfo.io/ip
curl ipecho.net/plain
curl www.trackip.net/i
```
## scp 文件上传下载命令

### 文件上传

```shell
scp <本地文件路径> root@<远程主机>:/path/on/remote/server/
```

### 上传目录

```shell
scp -r "<本地目录路径>" root@<远程主机>:/path/on/remote/server/
```

目录会上传到远程服务器上，路径为 `/path/on/remote/server/<本地目录路径>`。