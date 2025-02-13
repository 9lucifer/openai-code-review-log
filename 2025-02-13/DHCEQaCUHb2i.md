### 代码主要改动

#### 1. KeywordController.java
- **改动**: `selectKeywordsDto` 类被重命名为 `SelectKeywordsDTO`。
- **作用**: 看起来是为了统一命名规范，将 `Dto` 的首字母大写。
- **代码缺陷**: 无明显缺陷。

#### 2. LoginController.java
- **改动**: `Response` 类被删除，`weixinQrCodeTicket` 方法返回类型从 `Response<String>` 改为 `Result`。
- **作用**: 可能是为了简化返回类型，使用自定义的 `Result` 类。
- **代码缺陷**: 删除 `Response` 类可能导致其他依赖此类的代码出现错误。

#### 3. OpenaiController.java
- **改动**: 
  - 新增 `@Value` 注解用于获取配置文件中的属性。
  - `stopChat` 方法中，从使用 `HttpURLConnection` 发送请求改为使用 `RestTemplate`。
  - `speech` 方法中，`Query` 类被重命名为 `AgentQuery`，`WsAnswer` 类被重命名为 `ChatAnswer`。
  - 新增 `AgentAnswer` 类。
- **作用**: 
  - 使用配置文件中的属性，提高代码的可配置性。
  - 使用 `RestTemplate` 简化 HTTP 请求的发送。
  - 使用新的 DTO 类来处理数据。
- **代码缺陷**: 
  - `stopChat` 方法中，`stopUri` 的值可能需要从配置文件中获取。
  - `speech` 方法中，`ChatQuery.Message` 类可能需要进一步优化。

#### 4. AIWebSocketHandler.java
- **改动**: 
  - 新增 `@Value` 注解用于获取配置文件中的属性。
  - 使用 `RestTemplate` 发送 HTTP 请求。
  - 使用新的 DTO 类来处理数据。
  - 删除了与原版 AI 后端的大模型之间的 ws 协议部分的代码。
- **作用**: 
  - 使用配置文件中的属性，提高代码的可配置性。
  - 使用 `RestTemplate` 简化 HTTP 请求的发送。
  - 使用新的 DTO 类来处理数据。
- **代码缺陷**: 
  - `createModelClient` 方法可能需要进一步优化。
  - `sendToModel` 方法中，`Query` 类可能需要进一步优化。

#### 5. WebSocketChatClient.java
- **改动**: 
  - `WsAnswer` 类被重命名为 `ChatAnswer`。
  - 使用新的 DTO 类来处理数据。
- **作用**: 使用新的 DTO 类来处理数据。
- **代码缺陷**: 无明显缺陷。

#### 6. application.yml
- **改动**: 添加了 `ai` 配置项，包括 `appKey`、`appSecret`、`agent` 和 `chatUri`。
- **作用**: 提供了 AI 相关的配置。
- **代码缺陷**: 无明显缺陷。

#### 7. tinymce/plugins/autosave/plugin.js
- **改动**: 修改了 `getAutoSavePrefix` 函数中的参数名称。
- **作用**: 为了与新的 DTO 类保持一致。
- **代码缺陷**: 无明显缺陷。

#### 8. tinymce/plugins/kityformula-editor/kityFormula.html
- **改动**: 修改了 `getQueryVariable` 函数中的参数名称。
- **作用**: 为了与新的 DTO 类保持一致。
- **代码缺陷**: 无明显缺陷。

#### 9. table.html
- **改动**: 将表单提交事件处理器从 `user-query` 改为 `user-chatQuery`。
- **作用**: 为了与新的 DTO 类保持一致。
- **代码缺陷**: 无明显缺陷。

#### 10. treetable.html
- **改动**: 将表单提交事件处理器从 `power-query` 改为 `power-chatQuery`。
- **作用**: 为了与新的 DTO 类保持一致。
- **代码缺陷**: 无明显缺陷。

#### 11. deptment.html
- **改动**: 将表单提交事件处理器从 `user-query` 改为 `user-chatQuery`。
- **作用**: 为了与新的 DTO 类保持一致。
- **代码缺陷**: 无明显缺陷。

#### 12. dict.html
- **改动**: 将表单提交事件处理器从 `dict-type-query` 改为 `dict-type-chatQuery`。
- **作用**: 为了与新的 DTO 类保持一致。
- **代码缺陷**: 无明显缺陷。

#### 13. log.html
- **改动**: 将表单提交事件处理器从 `dict-type-query` 改为 `dict-type-chatQuery`。
- **作用**: 为了与新的 DTO 类保持一致。
- **代码缺陷**: 无明显缺陷。

#### 14. power.html
- **改动**: 将表单提交事件处理器从 `user-query` 改为 `user-chatQuery