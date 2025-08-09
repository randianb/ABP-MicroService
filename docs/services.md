# 服务说明

- **AuthServer.Host**
  - 职责：统一认证授权中心（Authority）
  - 关键配置：`ConnectionStrings:Default`、`CorsOrigins`、`Redis`、`ElasticSearch`、`RabbitMQ`
  - 示例端点：`http://localhost:53362`

- **InternalGateway.Host**
  - 职责：内部 API 网关，供服务间或内部应用访问
  - 关键配置：`AuthServer:Authority`、`AuthServer:ApiName`、`ReRoutes`、`GlobalConfiguration:BaseUrl`

- **WebAppGateway.Host**
  - 职责：面向前端的 API 网关
  - 关键配置：`App:CorsOrigins`、`AuthServer:Authority`、`ReRoutes`、`RemoteServices`

- **BaseService.Host**
  - 职责：基础领域能力（用户/租户/字典等示例）
  - 关键配置：`App:CorsOrigins`、`ConnectionStrings:Default`、`Redis`、`ElasticSearch`、`AuthServer:Authority`

- **Business.Host**
  - 职责：业务域示例服务
  - 关键配置：`App:CorsOrigins`、`ConnectionStrings:Business`、`IdentityClients:Default`（客户端凭据）

- **FileStorage.Host**
  - 职责：文件存储与上传下载
  - 关键配置：`ConnectionStrings:FileStorage`、`AuthServer:Authority`、`App:CorsOrigins`