# 配置指南

- **数据库**
  - `ConnectionStrings:Default`：公共库（示例为 `ABP`）
  - `ConnectionStrings:Business`：业务库
  - `ConnectionStrings:FileStorage`：文件存储库

- **认证中心**
  - `AuthServer:Authority`：认证服务器地址（如 `http://localhost:53362`）
  - `IdentityClients:Default`（出现在 `Business.Host`）：客户端凭据用于调用其他服务

- **跨域**
  - `App:CorsOrigins`（服务侧）与 `CorsOrigins`（AuthServer 顶层）需包含前端来源

- **缓存与消息**
  - `Redis:Configuration`：Redis 实例地址
  - `RabbitMQ:*`（在 AuthServer 示例）：可选事件总线配置

- **日志**
  - `ElasticSearch:Url`：可选，指向 ES 服务

- **网关**
  - `ReRoutes`：上游到下游的路径映射
  - `GlobalConfiguration:BaseUrl`（InternalGateway）：网关基础地址
  - `RemoteServices:Default:BaseUrl`（WebAppGateway）：默认下游地址

- **示例片段**
  - `Business.Host` 客户端配置：
    - `IdentityClients:Default` 包含 `ClientId`、`ClientSecret`、`Scope`（如 `InternalGateway BaseService`）