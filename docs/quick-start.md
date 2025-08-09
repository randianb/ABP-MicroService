# 快速开始

- **准备环境**
  - .NET SDK 6+/7+
  - SQL Server (本地或远程)
  - Redis
  - ElasticSearch (可选)
  - Node.js 14+（仅前端）

- **一键脚本**
  - Windows: 运行 `run/run_services.bat` 启动后端服务，`run/run_web.bat` 启动前端

- **服务端口（默认）**
  - 认证中心 `AuthServer.Host`: Authority `http://localhost:53362`
  - 内部网关 `InternalGateway.Host`: BaseUrl `http://localhost:59682`
  - Web 网关 `WebAppGateway.Host`
    - 下游：`BaseService` 55389、`Business` 51186 等
  - 业务服务 `Business.Host`: 默认本地端口见启动日志
  - 基础服务 `BaseService.Host`: 默认本地端口见启动日志
  - 文件服务 `FileStorage.Host`: 默认本地端口见启动日志

- **前端**
  - 见 `WebApp/vue/README.zh-CN.md`

- **默认账号（演示）**
  - 体验地址与演示账号见根 `README.md`

- **常见问题**
  - 启动前请确认 `appsettings.json` 中连接串与 `CorsOrigins`、`Authority` 等配置与本地环境一致。