### 代码主要改动

#### package-lock.json
1. **新增依赖**:
   - `dompurify`：用于清理HTML内容，防止XSS攻击。
   - `crypto-js`：用于加密和解密数据。
   - `element-plus`：Vue.js 3.0的UI库。
   - `highlight.js`：用于高亮显示代码。
   - `marked`：用于解析Markdown格式的内容。
   - `mammoth`：用于将Word文档转换为HTML。
   - `particles.vue3`：用于创建粒子动画效果。
   - `@types/trusted-types`：用于类型定义，增强安全性。

2. **更新依赖**:
   - `@amap/amap-jsapi-loader`：更新版本，但保留相同的许可证和完整性。
   - `dingbat-to-unicode`：更新版本。
   - `highlight.js`：更新版本，并指定Node.js版本要求。
   - `marked`：更新版本，并指定Node.js版本要求。

3. **移除依赖**:
   - 无。

#### package.json
1. **新增依赖**:
   - 与package-lock.json中相同的新增依赖。

#### src/App.vue
1. **新增路由**:
   - 添加了“map”路由，但被注释掉。

#### src/components/AIdemo.vue
1. **组件结构改动**:
   - 添加了侧边栏组件，用于显示聊天历史记录。
   - 添加了Markdown渲染功能，用于显示格式化的代码和文本。

2. **功能改动**:
   - 添加了发送和停止发送消息的功能。
   - 添加了获取聊天历史记录的功能。

3. **代码优化**:
   - 使用了Vue 3的Composition API。

#### src/router/index.ts
1. **路由改动**:
   - 添加了“Live”和“Map”路由。

#### src/views/Home.vue
1. **模板改动**:
   - 将Swiper组件替换为Element Plus的Carousel组件。

2. **代码优化**:
   - 使用了Vue 3的Composition API。

### 新提交代码作用

1. **新增功能**:
   - 添加了侧边栏组件，用于显示聊天历史记录。
   - 添加了Markdown渲染功能，用于显示格式化的代码和文本。
   - 添加了发送和停止发送消息的功能。
   - 添加了获取聊天历史记录的功能。

2. **代码优化**:
   - 使用了Vue 3的Composition API。
   - 使用了Element Plus的Carousel组件。

### 代码缺陷

1. **潜在的安全问题**:
   - `dompurify`用于清理HTML内容，但未指定配置选项，可能存在安全风险。

2. **代码风格**:
   - 代码中存在一些未注释的代码，建议添加注释以提高代码可读性。

3. **测试**:
   - 未提供测试用例，建议添加单元测试以确保代码质量。

4. **性能**:
   - 使用了大量的DOM操作和动画效果，可能影响页面性能。

5. **依赖版本**:
   - 部分依赖版本较高，可能与其他依赖存在兼容性问题。