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

## 实验三 工程结构与巡检页面整理

在实验二工程上把网络测试页整理为校园巡检页面，代码拆分为三个文件：

| 文件 | 职责 |
| --- | --- |
| MainActivity.kt | 系统入口，设置 Compose 内容，安排请求与结果更新 |
| InspectionScreen.kt | 显示巡检数据、按钮与回调、计算未检查数量 |
| InspectionNetwork.kt | 创建 OkHttpClient、执行请求、处理响应和异常 |

网络库：`com.squareup.okhttp3:okhttp:4.12.0`（在 `app/build.gradle.kts` 的 dependencies 中声明）。

## 运行方法

1. 用 Android Studio 打开本工程，等待 Gradle Sync 完成。
2. 选择任意 Android 9（API 28）以上的模拟器或真机，点击 Run 'app'。
3. 页面显示巡检员姓名、实验室 A203、总数 10、已检查 3、未检查 7。
4. 点击"请求 A203"或"请求 A204"，页面显示请求地址、HTTP 状态码和回显 JSON。

接口：`https://httpbin.org/get?room=A203`（HTTP 明文仅用于教学对比，见 network_security_config.xml）。
