# 实验二 Android 网络访问与 Git 个人仓库

## 实验目标
在 Kotlin Compose 项目中完成真实网络请求，观察 HTTP 明文策略配置前后的差异。

## 运行方式
用 Android Studio 打开本工程，等待 Gradle Sync 完成，
选择任意 Android 9（API 28）以上的模拟器，点击 Run 'app'。

## 接口地址
- HTTPS: https://httpbin.org/get?room=A203
- HTTP:  http://httpbin.org/get?room=A203

## 安全说明
HTTP 仅用于教学对比，实际服务优先使用 HTTPS。
network_security_config.xml 中全局禁止明文，仅对测试域名 httpbin.org 单独放行。