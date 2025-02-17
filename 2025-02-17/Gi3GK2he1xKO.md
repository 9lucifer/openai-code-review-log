### 代码主要改动

1. **pom.xml 文件**:
   - 移除了 `xstream` 和 `dom4j` 依赖。
   - 添加了 `org.apache.commons:commons-lang3:3.12.0` 依赖。
   - 移除了 `org.apache.httpcomponents:httpclient:4.5.13`、`org.java-websocket:Java-WebSocket:1.5.2` 和 `org.apache.commons:commons-lang3:3.12.0` 依赖。
   - 添加了 `org.springframework.boot:spring-boot-starter-jdbc` 依赖。
   - 移除了 `com.alibaba.nls:nls-sdk-transcriber:2.2.1` 依赖。

2. **SecurityConfig.java 文件**:
   - 添加了 `HttpStatusEntryPoint` 和 `UsernamePasswordAuthenticationToken` 类的导入。
   - 在 `filterChain` 方法中添加了异常处理，设置了 `HttpStatusEntryPoint` 和 `UsernamePasswordAuthenticationToken`。

3. **DialogController.java 文件**:
   - 将 `updateTitle` 方法更改为 `updateDialog`。

4. **LoginController.java 文件**:
   - 添加了 `RequiredArgsConstructor` 注解。
   - 添加了 `JwtUtil`、`UserDetailsServiceImpl` 和 `UserSignService` 类的导入。
   - 在 `weChatQrCodeTicket` 方法中添加了 `userDetails` 和 `SecurityContextHolder` 的设置。
   - 在 `checkLogin` 方法中添加了 `userDetails` 和 `SecurityContextHolder` 的设置。

5. **OpenaiController.java 文件**:
   - 添加了 `RequiredArgsConstructor` 和 `Slf4j` 注解。
   - 添加了 `RestTemplate`、`Gson`、`DialogService` 和 `UserSignService` 类的导入。
   - 在 `FormalChat` 方法中移除了对 `HttpURLConnection` 的使用，改为使用 `RestTemplate`。
   - 在 `stopChat` 方法中移除了对 `HttpURLConnection` 的使用，改为使用 `RestTemplate`。
   - 在 `chatSearch` 方法中添加了 `SearchRequestDTO` 类的导入和使用。
   - 在 `speech` 方法中添加了 `ChatRequestDTO` 类的导入和使用。
   - 在 `doInvokeVoice` 方法中添加了 `ChatRequestDTO` 类的导入和使用。
   - 在 `httpAgentChat` 方法中添加了 `AgentRequestDTO` 类的导入和使用。

6. **UserController.java 文件**:
   - 添加了 `UserSignService`、`UserDetailsServiceImpl` 和 `JwtUtil` 类的导入。
   - 在 `sendSmsCode` 方法中添加了 `clientIp` 的获取和记录。

7. **AgentQuery.java 文件**:
   - 将 `AgentQuery` 类重命名为 `AgentRequestDTO`。

8. **AgentAnswer.java 文件**:
   - 将 `AgentAnswer` 类重命名为 `AgentResponseDTO`。

9. **WsQuery.java 文件**:
   - 将 `WsQuery` 类重命名为 `ChatDTO`。

10. **SignAnswer.java 文件**:
    - 将 `SignAnswer` 类重命名为 `ChatHttpResponseDTO`。

11. **ChatQuery.java 文件**:
    - 将 `ChatQuery` 类重命名为 `ChatRequestDTO`。

12. **ChatAnswer.java 文件**:
    - 将 `ChatAnswer` 类重命名为 `ChatWsResponseDTO`。

13. **LoginPwdDTO.java 文件**:
    - 删除了 `LoginPwdDTO` 类。

14. **SearchRequestDTO.java 文件**:
    - 新建了 `SearchRequestDTO` 类。

15. **StopQuery.java 文件**:
    - 将 `StopQuery` 类重命名为 `StopRequestDTO`。

16. **StopResult.java 文件**:
    - 将 `StopResult` 类重命名为 `StopResponseDTO`。

17. **MessageTextEntity.java 文件**:
    - 删除了 `MessageTextEntity` 类。

18. **SmsCodeAuthenticationToken.java 文件**:
    - 删除了 `SmsCodeAuthenticationToken` 类。

19. **User.java 文件**:
    - 修改了 `User` 类的构造方法。

20. **TokenResponse.java 文件**:
    - 删除了 `TokenResponse` 类。

21. **AIWebSocketHandler.java 文件**:
    - 添加了 `RequiredArgsConstructor` 和 `Slf4j` 注解。
    - 在 `onMessage` 方法中添加了 `ChatWsResponseDTO` 类的导入和使用。

22. **UserMapper.java 文件**:
    - 将 `getUserByPhone` 方法的参数从 `String phoneNumber` 修改为 `String phone`。

23. **