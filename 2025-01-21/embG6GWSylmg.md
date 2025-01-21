### 代码评审

#### 1. 代码主要改动

**ProcessController.java**
- 新增了 ProcessController 类，用于处理与流程相关的 RESTful API 请求。
- 包含了获取流程列表、添加流程、更新流程和逻辑删除流程四个方法。

**AgendaMapper.java**
- 移除了 getAll 和 getById 方法，因为这些方法与流程处理无关。

**ProcessMapper.java**
- 新增了 ProcessMapper 接口，定义了获取流程列表、插入流程、删除流程和更新流程的方法。

**ProcessService.java**
- 新增了 ProcessService 接口，定义了与流程相关的业务逻辑。

**ProcessServiceImpl.java**
- 实现了 ProcessService 接口，通过 ProcessMapper 完成流程相关的数据库操作。

**application.yml**
- 修改了日志级别，增加了 top.miqiu.lakesword_backend 和 org.springframework.security 的日志级别。

**AgendaMapper.xml**
- 移除了 addAgenda 和 getById 方法，因为这些方法与流程处理无关。

**ProcessMapper.xml**
- 新增了 insertProcess、deleteProcess、updateProcess 和 getProcessByAgendaId 方法，用于处理流程相关的数据库操作。

#### 2. 新提交代码作用

- **ProcessController.java**: 提供了与流程相关的 RESTful API 请求处理，方便前端调用。
- **ProcessMapper.java & ProcessServiceImpl.java**: 实现了流程相关的数据库操作，保证了数据的正确性。
- **application.yml**: 修改了日志级别，方便调试和监控。

#### 3. 代码缺陷

- **ProcessController.java**: 
  - 添加、更新和删除流程的方法没有返回具体的操作结果，如成功或失败信息。
  - 没有对输入参数进行校验，如 agendaId 和 processId 是否为空。

- **ProcessMapper.xml**:
  - deleteProcess 方法只将 is_deleted 字段设置为 1，但没有将 process 表中的其他相关数据删除，如流程相关的评论、附件等。

- **ProcessServiceImpl.java**:
  - 没有对数据库操作进行异常处理，如查询结果为空或更新失败等。

#### 4. 建议

- 在 ProcessController.java 中，添加具体的操作结果返回，方便前端了解操作成功或失败。
- 在 ProcessMapper.xml 中，删除 process 表中与流程相关的其他数据。
- 在 ProcessServiceImpl.java 中，添加异常处理，保证程序的健壮性。
- 在添加、更新和删除流程的方法中，对输入参数进行校验，确保数据的正确性。