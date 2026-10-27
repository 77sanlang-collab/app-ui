# Parcly 小红书与拼多多测试版

[下载安装包](https://github.com/77sanlang-collab/app-ui/releases) · [查看打包进度](https://github.com/77sanlang-collab/app-ui/actions)

在 Releases 中选择 `parcly-xhs-pdd-test-arm64.apk`，适用于 OPPO Find X8。
只有自动打包成功后才会出现下载文件。仓库不是上游官方发行版。

## 改动与边界

- 设置页新增小红书订单网页入口：`https://www.xiaohongshu.com/order/list`。
- 小红书目前只提供页面入口，尚未实现自动导入或自动更新包裹。
- 拼多多网页请求打开官方 App 时，显示「打开 App」按钮，不再直接拦截；兼容 Android Intent 形式。
- 打开官方 App 不等于向本应用授权登录，手机号登录引起另一端退出的问题尚未解决。
- 暂不加入抖音入口。
- 独立包名 `com.example.pickup_app.xhs_pdd_test`，显示为「Parcly 测试版」，可与原版并存；数据不会自动迁移。
- 使用测试签名。后续不同构建可能需要卸载旧测试版再安装；卸载会清除测试版数据。

安装后：进入「设置与平台绑定 → 新平台订单页测试 → 小红书订单页（测试）」，自行登录查看订单和物流。
拼多多仍在原平台入口测试；页面请求唤起官方 App 时点击底部提示中的「打开 App」。

## 来源与构建

基于 [Granter-z/parcly](https://github.com/Granter-z/parcly) 的固定提交 `0e4c7739205b368ab9bed3299f963a3e6fd9cf91`。
`patches/parcly.patch` 包含全部修改。Actions 下载固定源码、应用补丁、检查页面、运行测试、打包并发布测试 APK。
上游采用 GPL-3.0；保留原版权及许可证，构建产物同时附带对应完整源码 ZIP。

本地验证：修改页面静态检查通过，433 项现有测试通过；未在真实手机上验证登录和跳转。
