### 代码主要改动

1. **pom.xml 文件改动**:
   - 添加了多个依赖项，包括 `commons-lang`, `hutool-all`, `httpcore`, `httpclient`, `commons-io`, 和 `fastjson`。
   - `fastjson` 的版本为 `1.2.83`，兼容 Java 1.8。

2. **src/main/java 目录下新增文件**:
   - `SparkAiController.java`: 用于处理 Spark AI 相关的请求。
   - `XunfeiController.java`: 用于处理讯飞语音相关的请求。
   - `FileReq.java` 和 `OpenReq.java`: 用于定义讯飞语音请求的数据结构。
   - `SparkApiDemo.java`, `IMessage.java`, 和 `SparkApiResponse.java`: 用于处理 Spark API 相关的请求。
   - `SpeedTranscriptionMain.java`: 用于处理讯飞语音的极速转写。
   - `Ifasrdemo.java`: 用于处理讯飞语音的语音识别。
   - `ApiResponse.java`, `Content.java`, `Cw.java`, `Json1Best.java`, `Lattice.java`, `Lattice2.java`, `OrderInfo.java`, `OrderResult.java`, `Rt.java`, `St.java`, `Ws.java`: 用于处理讯飞语音请求的 JSON 数据结构。
   - `AbstractSignature.java`, `LfasrSignature.java`, 和 `CryptTools.java`: 用于处理讯飞语音请求的签名。
   - `HttpConnector.java` 和 `HttpUtil.java`: 用于处理 HTTP 请求。
   - `TempFileUtils.java`: 用于处理临时文件的创建和删除。
   - `Authentication.java`, `FileCaller.java`, `FileResp.java`, `OpenCaller.java`, 和 `OpenResp.java`: 用于处理讯飞语音请求的认证和响应。

3. **src/main/resources 目录下新增文件**:
   - `application.yml`: 修改了服务器端口和最大文件大小。
   - `audio/xxx.wav`: 新增了一个音频文件。
   - `output/test.txt`: 新增了一个文本文件。

### 新提交代码作用

- 添加了 `commons-lang`, `hutool-all`, `httpcore`, `httpclient`, `commons-io`, 和 `fastjson` 依赖项，以支持代码中使用的相关库。
- 实现了 Spark AI 和讯飞语音的 API 请求处理。
- 定义了讯飞语音请求的数据结构。
- 实现了讯飞语音的极速转写和语音识别功能。
- 实现了讯飞语音请求的签名和认证。
- 实现了 HTTP 请求处理。
- 实现了临时文件的创建和删除。

### 代码缺陷

1. **依赖项版本**:
   - `fastjson` 的版本为 `1.2.83`，可能不兼容最新的 Java 版本。
   - 其他依赖项的版本也需要根据实际需求进行选择。

2. **代码结构**:
   - 代码结构较为复杂，需要进一步优化和整理。
   - 部分代码存在重复，需要进行重构。

3. **异常处理**:
   - 代码中存在一些异常处理，但不够完善。
   - 建议添加更多的异常处理，以提高代码的健壮性。

4. **代码注释**:
   - 代码中缺少注释，难以理解代码的功能和实现细节。
   - 建议添加必要的注释，以提高代码的可读性。

5. **测试**:
   - 代码缺少测试，难以保证代码的正确性。
   - 建议添加单元测试和集成测试，以提高代码的质量。