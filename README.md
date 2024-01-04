# Docker-ProfileMaker-vol2

使用Docker制作Linux内存取证中vol2需要的profile
本项目默认的内核版本如下所示，版本可以根据需要自行更改

```plaintext
Linux version 5.10.0-21-amd64 (debian-kernel@lists.debian.org) (gcc-10 (Debian 10.2.1-6) 10.2.1 20210110, GNU ld (GNU Binutils for Debian) 2.35.2) #1 SMP Debian 5.10.162-1 (2023-01-21)
```

Tips:使用前需要把以下四个文件放到 Dockerfile 同一目录下，构建好后进入容器，dwarf 文件在/app目录下

​		可以到 [官方仓库](https://debian.sipwise.com/debian-security/pool/main/l/linux/)下载以下几个文件

```
linux-headers-5.10.0-21-amd64_5.10.162-1_amd64.deb
linux-headers-5.10.0-21-common_5.10.162-1_all.deb
linux-image-5.10.0-21-amd64-dbg_5.10.162-1_amd64.deb
linux-image-5.10.0-21-amd64-unsigned_5.10.162-1_amd64.deb
```

具体使用命令如下

```bash
docker build --tag profile:v1 . 
docker run -it -p 2022:22 profile bash
```

如果这个项目对你有帮助，请帮我点个Star⭐吧( •̀ ω •́ )y

详细教程可以查看[我的博客](https://goodlunatic.github.io/)
