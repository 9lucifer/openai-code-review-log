### 代码评审

#### 主要改动

1. **pom.xml**:
   - 添加了Spring Boot的AMQP和WebSocket依赖。
   - 添加了Spring AMQP的测试依赖。

2. **WebSocketConfig.java**:
   - 新增了WebSocket配置类，用于注册WebSocket处理器。

3. **NewsController.java**:
   - 添加了获取新闻详情的接口。

4. **OpenaiController.java**:
   - 移除了`@GetMapping(value = "/chat")`，可能是因为新增了WebSocket的聊天功能。

5. **Answer.java, Message.java, Query.java**:
   - 新增了DTO类，用于封装聊天消息的参数。

6. **News.java**:
   - `newsId`和`isDeleted`字段的数据类型从`long`更改为`Long`。

7. **NewsDetail.java, NewsSummary.java**:
   - 新增了实体类，用于表示新闻详情和新闻摘要。

8. **AIWebSocketHandler.java**:
   - 新增了WebSocket处理器类，用于处理WebSocket连接和消息。

9. **NewsMapper.java**:
   - 更改了`getNewsList`和`addNews`方法的结果类型和参数类型。
   - 新增了`getNewsById`和`getNewsByTitle`方法。

10. **NewsService.java**:
    - 更改了`getNews`方法的结果类型。
    - 新增了`getNewsById`方法。

11. **NewsServiceImpl.java**:
    - 更改了`getNews`和`addNews`方法的结果类型。
    - 新增了`getNewsById`方法。
    - 使用MongoTemplate进行数据操作。

12. **WebSocketChatClient.java**:
    - 重命名文件并修改了类名。
    - 移除了`ChatMessage`类。
    - 更改了发送消息的格式。

13. **NewsMapper.xml**:
    - 更改了`addNews`和`updateNews`方法的参数类型。
    - 新增了`getNewsList`, `getNewsById`, 和`getNewsByTitle`的SQL语句。

#### 新提交代码作用

1. **pom.xml**:
   - 新增的依赖使得项目支持AMQP和WebSocket功能。

2. **WebSocketConfig.java**:
   - 注册了WebSocket处理器，用于处理WebSocket连接和消息。

3. **NewsController.java**:
   - 新增了获取新闻详情的接口，方便用户查看新闻内容。

4. **AIWebSocketHandler.java**:
   - 处理WebSocket连接和消息，实现与AI模型的交互。

5. **NewsMapper.java, NewsService.java, NewsServiceImpl.java**:
   - 更新了新闻相关的数据访问层代码，支持新闻详情和新闻摘要的查询和操作。

6. **WebSocketChatClient.java**:
   - 重命名文件并修改了类名，使得代码结构更清晰。

#### 代码缺陷

1. **News.java**:
   - `isDeleted`字段从`long`更改为`Long`，可能导致数据类型转换错误。

2. **NewsMapper.xml**:
   - `addNews`和`updateNews`的SQL语句中使用了`#{content}`，但没有指定`content`字段的数据类型，可能导致SQL执行错误。

3. **AIWebSocketHandler.java**:
   - `createModelClient`方法中使用了硬编码的appKey和appSecret，安全性较低。
   - `sendToModel`方法中使用了硬编码的appKey，安全性较低。

4. **WebSocketChatClient.java**:
   - `sendMessage`方法中使用了硬编码的appKey和appSecret，安全性较低。

5. **代码风格**:
   - 代码风格不统一，例如变量命名、方法命名等。

#### 建议

1. **数据类型**:
   - 确保数据类型的一致性，避免数据类型转换错误。

2. **安全性**:
   - 将appKey和appSecret存储在配置文件中，并使用环境变量或加密方式保护敏感信息。

3. **代码风格**:
   - 统一代码风格，提高代码可读性和可维护性。