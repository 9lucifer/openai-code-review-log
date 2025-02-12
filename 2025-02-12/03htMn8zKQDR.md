### 代码主要改动

#### WebSocketConfig.java
- 移除了 SpeechWebSocketHandler 的相关配置，包括导入语句、资源注入和 WebSocketHandlerRegistry 中的注册。
- 代码行数减少，移除了与语音相关的 WebSocket 配置。

#### AgendaController.java
- 添加了四个新的 GET 请求映射方法，用于获取日程类型、日期和特定日期的日程。
- 添加了对应的控制器方法，调用 AgendaService 中的新方法。

#### DialogController.java
- 添加了更新对话标题和删除对话的 POST 和 DELETE 请求映射方法。
- 添加了对应的控制器方法，调用 DialogService 中的新方法。

#### OpenaiController.java
- 移除了与语音相关的代码，包括 SpeechUtil 类的引用和语音识别相关的请求处理。
- 添加了新的 GET 请求映射方法 `/speech`，用于处理语音分析请求。
- 修改了 `/chat/search` 方法，移除了与语音相关的代码。

#### Question.java
- 修改了 Question 类的构造函数，移除了 List<Message> 的参数。
- 修改了 Question 类的字段，将 List<Message> 替换为 Message。

#### Dialog.java
- 添加了 title 字段，用于存储对话标题。

#### AIWebSocketHandler.java
- 在 `sendToModel` 方法中添加了同步关键字，以避免并发问题。
- 修改了 Dialog 对象的创建逻辑，添加了 title 字段。

#### SpeechWebSocketHandler.java
- 删除了 SpeechWebSocketHandler 类，移除了语音相关的 WebSocket 处理器。

#### AgendaMapper.java
- 添加了三个新的方法，用于获取日程类型、日期和特定日期的日程。

#### DialogMapper.java
- 添加了删除对话和根据用户删除对话的方法。

#### AgendaService.java
- 添加了三个新的方法，用于获取日程类型、日期和特定日期的日程。

#### DialogService.java
- 添加了更新对话标题和根据用户删除对话的方法。

#### AgendaServiceImpl.java
- 添加了三个新的方法实现，用于获取日程类型、日期和特定日期的日程。

#### DialogServiceImpl.java
- 添加了两个新的方法实现，用于更新对话标题和根据用户删除对话。

#### UserSignServiceImpl.java
- 修改了签到方法的实现，添加了根据用户 ID 查询 UserSign 对象的逻辑。

#### SpeechUtil.java
- 删除了 SpeechUtil 类，移除了语音相关的代码。

#### application.yml
- 移除了与阿里云语音识别相关的配置。

#### AgendaMapper.xml
- 添加了三个新的 SQL 查询语句，用于获取日程类型、日期和特定日期的日程。

#### DialogMapper.xml
- 添加了删除对话和根据用户删除对话的 SQL 语句。

#### UserSignMapper.xml
- 修改了插入和更新 UserSign 对象的 SQL 语句，添加了 second_sign、second_time、third_sign 和 third_time 字段。

### 新提交代码作用

- 添加了新的功能，包括获取日程类型、日期和特定日期的日程，更新对话标题和删除对话。
- 移除了与语音相关的功能，优化了代码结构。

### 代码缺陷

- 移除 SpeechWebSocketHandler 类时，可能遗漏了与语音相关的其他代码。
- 在 AIWebSocketHandler 类中添加同步关键字可能会导致性能问题。
- 在 UserSignServiceImpl 类中，查询 UserSign 对象的逻辑可能存在性能问题。

### 建议

- 在删除 SpeechWebSocketHandler 类时，要确保没有其他代码依赖于它。
- 在 AIWebSocketHandler 类中，可以优化同步逻辑，以提高性能。
- 在 UserSignServiceImpl 类中，可以考虑使用缓存或其他方法来提高查询性能。