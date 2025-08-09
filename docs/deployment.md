# 部署与运行

- **本地运行顺序（建议）**
  1. 配置数据库、Redis、ElasticSearch（可选）
  2. 运行 `AuthServer.Host`
  3. 运行 `BaseService.Host`、`Business.Host`、`FileStorage.Host`
  4. 运行 `InternalGateway.Host`、`WebAppGateway.Host`
  5. 前端运行 `WebApp/vue`

- **关键环境变量/配置**
  - `ConnectionStrings:*` 指定 SQL Server 连接
  - `Redis:Configuration` 指定 Redis 实例
  - `AuthServer:Authority` 指向认证中心地址
  - `App:CorsOrigins` 允许的前端来源
  - 网关 `ReRoutes` 与 `GlobalConfiguration:BaseUrl`

- **构建与发布**
  - 后端：`dotnet publish -c Release`，将 Host 发布产物部署到服务器
  - 前端：参见 `WebApp/vue/README.zh-CN.md` 的构建与发布章节

- **Docker（如需）**
  - `AuthServer.Host` 提供了 `Dockerfile` 示例，可参照进行容器化
  - 自行准备 SQLServer、Redis、ElasticSearch、RabbitMQ（如用）容器或外部服务

- **故障排查**
  - 认证失败：检查 `Authority`、客户端配置（`IdentityClients`）与 API 作用域
  - 跨域：检查前端访问域名是否在各服务 `CorsOrigins` 中
  - 网关 404：核对 `ReRoutes` 下游端口与实际运行端口是否一致