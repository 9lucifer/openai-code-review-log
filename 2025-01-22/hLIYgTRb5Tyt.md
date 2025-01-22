### 代码主要改动

1. **AchievementController.java**:
   - `@PostMapping("/update")` 改为 `@PutMapping("/update")` 在更新活动成果的方法上。
   - 原因可能是 `@PostMapping` 通常用于创建资源，而 `@PutMapping` 用于更新资源，更符合语义。

2. **GuestController.java**:
   - 新增了一个用于管理嘉宾信息的控制器 `GuestController`。
   - 包含获取所有嘉宾、添加嘉宾、更新嘉宾和删除嘉宾的方法。

3. **NewsController.java**:
   - 新增了一个用于管理新闻信息的控制器 `NewsController`。
   - 包含获取新闻、添加新闻、更新新闻和删除新闻的方法。

4. **ProcessController.java**:
   - 修改了 `getProcess` 方法的路径变量，从 `@PathVariable("agendaId")` 改为直接接收 `Long agendaId` 参数。
   - 修改了 `deleteProcess` 方法的路径变量，从 `@PathVariable Long processId` 改为直接接收 `Long processId` 参数。

5. **SpecialEventController.java**:
   - 新增了一个用于管理特殊活动的控制器 `SpecialEventController`。
   - 包含获取所有特殊活动、添加特殊活动、更新特殊活动和删除特殊活动的方法。

6. **Mapper 文件**:
   - 新增了 `GuestMapper`, `NewsMapper`, `SpecialEventMapper`，分别对应嘉宾、新闻和特殊活动的数据访问层接口。
   - 在这些接口中定义了增删改查的方法。

7. **Service 层**:
   - 新增了 `GuestService`, `NewsService`, `SpecialEventService`，分别对应嘉宾、新闻和特殊活动的业务逻辑层接口。
   - 在这些接口中定义了相关的方法。

8. **ServiceImpl 层**:
   - 新增了 `GuestServiceImpl`, `NewsServiceImpl`, `SpecialEventServiceImpl`，分别对应嘉宾、新闻和特殊活动的业务逻辑层实现。
   - 在这些实现中调用了对应的 Mapper 层方法。

9. **application.yml**:
   - 移除了 `logging` 配置项中的 `top.miqiu.lakesword_backend` 和 `org.springframework.security` 的 `debug` 级别配置。

10. **AgendaMapper.xml**:
    - 修改了 `insert` 和 `select` 的表名为 `agenda`，与数据库中的表名一致。

11. **Mapper 文件**:
    - 新增了 `GuestMapper.xml`, `NewsMapper.xml`, `SpecialEventMapper.xml`，包含了相应的 SQL 语句。

### 新提交代码作用

- 新增的控制器和业务逻辑层接口实现了嘉宾、新闻和特殊活动的增删改查功能。
- 新增的 Mapper 层接口和实现类实现了与数据库的交互。
- 修改的代码确保了方法的语义正确性。

### 代码缺陷

1. **AchievementController.java**:
   - 修改 `@PostMapping` 为 `@PutMapping` 可能需要调整前端请求方式。

2. **Mapper 文件**:
   - 新增的 Mapper 文件可能需要根据实际数据库表结构调整 SQL 语句。

3. **application.yml**:
   - 移除 `logging` 配置项可能导致日志级别无法正确设置。

4. **AgendaMapper.xml**:
   - 修改表名需要确保数据库中存在对应的表。

5. **Mapper 文件**:
   - 新增的 Mapper 文件可能存在 SQL 注入风险。

6. **ServiceImpl 层**:
   - 新增的 ServiceImpl 层实现类可能存在逻辑错误。

7. **代码风格**:
   - 部分代码风格不符合 Java 代码规范，例如缩进、命名等。