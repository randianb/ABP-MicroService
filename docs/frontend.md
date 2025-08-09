# 前端 WebApp

- **代码位置**
  - `WebApp/vue`

- **文档与启动**
  - 参考 `WebApp/vue/README.zh-CN.md`
  - 启动后通过 `WebAppGateway` 访问后端，注意 `CorsOrigins` 与 `Authority` 的匹配

- **常见配置**
  - 网关地址：在前端环境变量或配置文件中指向 `WebAppGateway`
  - 登录：指向 `AuthServer` 的授权地址