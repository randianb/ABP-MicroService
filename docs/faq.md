# FAQ

- **登录失败/401**
  - 检查前端配置的 `Authority` 与服务端 `AuthServer:Authority` 是否一致
  - 客户端凭据是否正确（`IdentityClients`）以及 Scope 是否包含目标 API

- **跨域报错**
  - 将前端访问域名加入各服务 `App:CorsOrigins` 与 `AuthServer` 的 `CorsOrigins`

- **API 网关 404/502**
  - 校验 `ReRoutes` 中的 `DownstreamHostAndPorts` 端口与服务实际监听端口

- **数据库连接失败**
  - 检查 `ConnectionStrings:*`、SQL Server 账户/防火墙/网络连通

- **Redis 连接失败**
  - 校验 `Redis:Configuration` 地址与端口，确认服务已启动