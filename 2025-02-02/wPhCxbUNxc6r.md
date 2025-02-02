### 代码主要改动：

1. **pom.xml 文件修改**:
   - 添加了三个新的依赖：
     - `spring-boot-starter-amqp`: 用于集成 AMQP（高级消息队列协议），可能用于消息队列操作。
     - `spring-boot-starter-websocket`: 用于WebSocket通信，可能用于实时通信或交互。
     - `spring-rabbit-test`: 用于测试Spring AMQP，通常用于单元测试。

2. **WebSocketConfig.java 文件**:
   - 创建了一个新的配置类，用于配置WebSocket连接。
   - 定义了一个Bean `aiWebSocketHandler`，用于处理WebSocket消息。

3. **NewsController.java 文件**:
   - 添加了一个新的GET请求方法 `/detail`，用于获取新闻详情。

4. **OpenaiController.java 文件**:
   - 移除了 `@GetMapping(value = "/chat")` 注解，注释掉了相应的方法。

5. **新文件**:
   - `Answer.java`: 用于存储聊天回答的DTO。
   - `Message.java`: 用于存储消息的DTO。
   - `Query.java`: 用于存储查询的DTO。
   - `NewsDetail.java`: 用于存储新闻详情的实体。
   - `NewsSummary.java`: 用于存储新闻摘要的实体。
   - `AIWebSocketHandler.java`: 用于处理WebSocket消息，实现与AI模型的通信。

6. **NewsMapper.java 文件**:
   - 修改了 `getNewsList` 方法的返回类型为 `NewsSummary`。
   - 添加了新的方法 `getNewsById` 和 `getNewsByTitle`。

7. **NewsService.java 文件**:
   - 修改了 `getNews` 方法的返回类型为 `NewsSummary`。

8. **NewsServiceImpl.java 文件**:
   - 修改了 `getNews` 方法的实现，使用 `NewsSummary`。
   - 修改了 `getNewsById` 和 `addNews` 方法的实现，使用 `NewsSummary` 和 `NewsDetail`。
   - 修改了 `updateNews` 和 `deleteNews` 方法的实现，使用 `NewsSummary`。

9. **WebSocketChatClient.java 文件**:
   - 重命名了文件，从 `WebSocketChatClient.java` 到 `WebSocketChatClient.java`。
   - 修改了发送消息的代码，使用新的DTO类。

10. **NewsMapper.xml 文件**:
    - 修改了 `addNews` 方法的 `parameterType` 为 `NewsSummary`。
    - 添加了新的SQL查询语句，用于获取 `NewsSummary`。

### 新提交代码作用：

- **集成AMQP和WebSocket**: 通过添加依赖和配置类，项目现在可以支持消息队列和WebSocket通信。
- **增加新闻详情功能**: 通过添加新的控制器方法和实体类，用户现在可以获取新闻的详细信息。
- **AIWebSocketHandler**: 新的WebSocket处理器用于与AI模型进行通信，可能用于聊天机器人或其他交互式应用。

### 代码缺陷：

- **缺少单元测试**: 新添加的代码没有相应的单元测试，这可能导致未发现的bug。
- **日志记录不足**: 代码中缺少足够的日志记录，这使得调试和监控变得困难。
- **异常处理**: 代码中缺少异常处理，可能导致应用程序崩溃。
- **代码风格不一致**: 代码中存在不一致的命名规范和编程风格，这可能导致代码难以阅读和维护。

### 总结：

这次提交引入了新的功能，如新闻详情和WebSocket通信，同时也添加了一些新的DTO和实体类。然而，代码中存在一些缺陷，需要进一步的测试和改进。