适用于 OPPO Find X8 的 arm64 测试包。

- 小红书订单网页测试入口；不含自动包裹导入。
- 拼多多官方 App 唤起提示与 Android Intent 跳转调整；未解决双端登录互踢。
- 暂不加入抖音。
- 独立应用「Parcly 测试版」，可与原版并存，需要自行重新登录。
- 测试签名；不同构建可能无法直接覆盖安装。

在 Assets 中下载 `parcly-xhs-pdd-test-arm64.apk`。`parcly-test-source.zip` 是对应源码；`SHA256SUMS.txt` 是文件校验值。
构建通过代码检查和现有测试，但登录与跳转仍需真实手机验证。
