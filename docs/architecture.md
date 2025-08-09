# 架构说明

- **整体**
  - 基于 ABP vNext 的微服务体系，DDD 分层：Domain / Application / HttpApi / Host / EFCore
  - 统一认证（AuthServer）+ API 网关（InternalGateway、WebAppGateway）
  - 服务示例：BaseService、Business、FileStorage

- **网关职责**
  - `InternalGateway`：内网调用汇聚、内部 API 聚合，身份校验 `ApiName=InternalGateway`
  - `WebAppGateway`：面向前端的统一入口，配置若干 `ReRoutes` 转发至下游服务

- **基础设施**
  - 身份与授权：IdentityServer4/ABP Identity，Authority 来源 `AuthServer`
  - 数据：SQL Server（`ConnectionStrings` 中 `Default`、业务库等）
  - 缓存与消息：Redis、可选 RabbitMQ（在 `AuthServer` 中示例）
  - 日志：ElasticSearch（可选）

- **前端**
  - `WebApp/vue` 基于 vue-element-admin（i18n 分支），通过 `WebAppGateway` 访问后端 API