# Nacos Docker

## 项目地址

[https://github.com/joizhang/nacos-docker](https://github.com/joizhang/nacos-docker)

## 说明

最新 Nacos server 镜像，支持 Apple M1.

解决官方 `nacos/nacos-server` 报错的问题：
```
13:03:45.605 [main] ERROR org.springframework.boot.SpringApplication - Application run failed
com.alibaba.nacos.api.exception.runtime.NacosRuntimeException: ErrCode:500, ErrMsg:Function not implemented
        at com.alibaba.nacos.core.listener.StartingApplicationListener.loadPreProperties(StartingApplicationListener.java:164)
        at com.alibaba.nacos.core.listener.StartingApplicationListener.environmentPrepared(StartingApplicationListener.java:107)
        at com.alibaba.nacos.core.code.SpringApplicationRunListener.environmentPrepared(SpringApplicationRunListener.java:60)
        at org.springframework.boot.SpringApplicationRunListeners.lambda$environmentPrepared$2(SpringApplicationRunListeners.java:66)
        at java.util.ArrayList.forEach(ArrayList.java:1259)
        at org.springframework.boot.SpringApplicationRunListeners.doWithListeners(SpringApplicationRunListeners.java:120)
        at org.springframework.boot.SpringApplicationRunListeners.doWithListeners(SpringApplicationRunListeners.java:114)
        at org.springframework.boot.SpringApplicationRunListeners.environmentPrepared(SpringApplicationRunListeners.java:65)
        at org.springframework.boot.SpringApplication.prepareEnvironment(SpringApplication.java:343)
        at org.springframework.boot.SpringApplication.run(SpringApplication.java:301)
        at org.springframework.boot.SpringApplication.run(SpringApplication.java:1317)
        at org.springframework.boot.SpringApplication.run(SpringApplication.java:1306)
        at com.alibaba.nacos.Nacos.main(Nacos.java:35)
        at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
        at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
        at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
        at java.lang.reflect.Method.invoke(Method.java:498)
        at org.springframework.boot.loader.MainMethodRunner.run(MainMethodRunner.java:49)
        at org.springframework.boot.loader.Launcher.launch(Launcher.java:108)
        at org.springframework.boot.loader.Launcher.launch(Launcher.java:58)
        at org.springframework.boot.loader.PropertiesLauncher.main(PropertiesLauncher.java:467)
Caused by: com.alibaba.nacos.api.exception.NacosException: java.io.IOException: Function not implemented
        at com.alibaba.nacos.sys.file.WatchFileCenter$WatchDirJob.<init>(WatchFileCenter.java:186)
        at com.alibaba.nacos.sys.file.WatchFileCenter.registerWatcher(WatchFileCenter.java:94)
        at com.alibaba.nacos.core.listener.StartingApplicationListener.registerWatcher(StartingApplicationListener.java:170)
        at com.alibaba.nacos.core.listener.StartingApplicationListener.loadPreProperties(StartingApplicationListener.java:162)
        ... 20 common frames omitted
Caused by: java.io.IOException: Function not implemented
        at sun.nio.fs.LinuxWatchService.<init>(LinuxWatchService.java:64)
        at sun.nio.fs.LinuxFileSystem.newWatchService(LinuxFileSystem.java:47)
        at com.alibaba.nacos.sys.file.WatchFileCenter$WatchDirJob.<init>(WatchFileCenter.java:181)
        ... 23 common frames omitted
```

## 构建命令

```shell
docker build ./build -t="joizhang/nacos-server:2.2.0"
```

## 快速开始

```shell
docker-compose -f example/standalone-derby.yaml up
```

访问 [http://127.0.0.1:8848/nacos](http://127.0.0.1:8848/nacos)

