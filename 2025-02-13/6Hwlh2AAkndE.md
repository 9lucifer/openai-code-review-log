### 代码主要改动

#### 1. `package-lock.json` 文件改动
- 新增了以下依赖项：
  - `dompurify`：用于清理HTML内容，防止XSS攻击。
  - `highlight.js`：用于语法高亮显示。
  - `http-proxy-middleware`：用于设置HTTP代理。
  - `marked`：用于Markdown解析。
  - `particles.vue3`：用于创建粒子效果。
  - `swiper`：用于创建轮播图。
  - `@types/trusted-types`：用于类型定义。
- 更新了以下依赖项：
  - `@amap/amap-jsapi-loader`：用于加载高德地图API。
  - `axios`：用于发送HTTP请求。
  - `element-plus`：用于Vue UI组件库。
  - `vue`：用于Vue框架。

#### 2. `package.json` 文件改动
- 新增了以下依赖项：
  - `dompurify`：用于清理HTML内容，防止XSS攻击。
  - `highlight.js`：用于语法高亮显示。
  - `marked`：用于Markdown解析。

#### 3. `src/App.vue` 文件改动
- 在导航栏中添加了“AI智能体”链接。

#### 4. `src/components/AIdemo.vue` 文件改动
- 添加了AI智能体组件，包括聊天窗口、历史记录和侧边栏。
- 修改了聊天窗口的样式，添加了Markdown渲染和语法高亮。
- 修改了发送消息的逻辑，支持发送停止请求。

#### 5. `src/router/index.ts` 文件改动
- 删除了`AIdemo`路由。

#### 6. `src/views/Home.vue` 文件改动
- 将Swiper组件替换为Element Plus的Carousel组件。

### 新提交代码作用

- `dompurify`：用于清理HTML内容，防止XSS攻击。
- `highlight.js`：用于语法高亮显示。
- `marked`：用于Markdown解析。
- `particles.vue3`：用于创建粒子效果。
- `swiper`：用于创建轮播图。
- `@types/trusted-types`：用于类型定义。
- `http-proxy-middleware`：用于设置HTTP代理。

### 代码缺陷

- `src/components/AIdemo.vue` 文件中的`sendMessageToAi`函数中，WebSocket连接没有关闭，可能导致资源泄露。
- `src/components/AIdemo.vue` 文件中的`sendMessageToAi`函数中，没有处理WebSocket连接错误的情况。
- `src/components/AIdemo.vue` 文件中的`sendMessageToAi`函数中，没有处理发送停止请求的情况。
- `src/views/Home.vue` 文件中的Carousel组件的样式需要调整，以适应不同的屏幕尺寸。