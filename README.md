## CentOS7加装openwrt编译环境

### 脚本适用
采用最小安装CentOS7，配置好网络

### 使用方法
- 使用root权限执行脚本，正常情况执行完桌面就准备就绪了
```bash
# curl -fsSL https://raw.githubusercontent.com/panwenbin/centos7-openwrt-buildenv/master/centos7-openwrt-buildenv.sh | sh
```

### 可能需要的操作
git配置代理
```
$ git config --global http.proxy http://127.0.0.1:8080
```
取消
```
$ git config --global --unset http.proxy
```
git clone指定版本
```
$ git clone --branch v18.06.1 https://git.openwrt.org/openwrt/openwrt.git
```
更新安装组件并编译
```
$ cd openwrt

$ ./scripts/feeds update -a
$ ./scripts/feeds install -a

$ make menuconfig
$ make -j 2 V=99
```