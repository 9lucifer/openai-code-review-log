### 代码主要改动

1. **package-lock.json**:
   - `crypto-es` 和 `crypto-js` 的源从 `npmmirror.com` 更改为 `npmjs.org`。
   - `jquery`、`js-base64`、`recorder-manager`、`vconsole` 的源也进行了相同的更改。
   - `recorder-manager` 的版本号没有变化，但源地址已更新。

2. **src/App.vue**:
   - 移除了 `showAIPage` 的条件判断，直接显示 `index-bg`。
   - 将 `AI` 智能体的链接从 `javascript:;` 改为 `/AI`，并添加了对应的路由。
   - 移除了 `AIdemo` 组件的引用，并在模板中添加了注释。

3. **src/components/AIdemo.vue**:
   - 添加了历史对话记录功能，包括列表和标题。
   - 添加了聊天窗口的头部和底部，以及相关的样式。
   - 添加了发送消息到 AI 的函数 `sendMessageToAi`。
   - 添加了发送消息到 AI 的函数 `sendQuestion`。
   - 添加了加载历史记录的函数 `loadHistory`。
   - 添加了新的组件 `AI.vue`。

4. **src/router/index.ts**:
   - 将 `AIdemo` 路由更改为 `AI`。

5. **src/views/AI.vue**:
   - 新建了 `AI.vue` 组件，包含了聊天窗口、历史对话记录和推荐话题等功能。

6. **src/views/Live.vue**:
   - 在发送消息的输入框下方添加了发送按钮。
   - 添加了科大讯飞的相关依赖。

### 新提交代码作用

1. **更新源**:
   - 将 `crypto-es`、`crypto-js`、`jquery`、`js-base64`、`recorder-manager`、`vconsole` 的源从 `npmmirror.com` 更改为 `npmjs.org`，以使用官方源。

2. **添加历史对话记录**:
   - 在 `AIdemo.vue` 中添加了历史对话记录功能，方便用户查看之前的对话。

3. **添加聊天窗口**:
   - 在 `AIdemo.vue` 中添加了聊天窗口，包括头部、底部、消息列表和输入框。

4. **添加推荐话题**:
   - 在 `AI.vue` 中添加了推荐话题功能，方便用户快速发起对话。

5. **添加科大讯飞相关依赖**:
   - 在 `Live.vue` 中添加了科大讯飞的相关依赖，用于语音识别和语音合成。

### 代码缺陷

1. **代码风格**:
   - 代码风格不一致，建议统一代码风格。

2. **注释**:
   - 部分代码缺少注释，建议添加必要的注释。

3. **性能**:
   - `AIdemo.vue` 中的 `sendMessageToAi` 函数可能会造成性能问题，建议优化代码。

4. **安全性**:
   - 使用 `localStorage` 存储用户信息可能存在安全隐患，建议使用更安全的存储方式。

5. **依赖**:
   - `AI.vue` 中添加了多个依赖，建议进行依赖管理，避免不必要的依赖。