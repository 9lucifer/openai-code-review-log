根据提供的代码变更记录，以下是主要更改和更新：

**1. 依赖项更新**:

*   移除了 `@iconify/vue` 依赖项。
*   添加了 `@vitejs/plugin-vue`、`@vue/tsconfig`、`less`、`less-loader`、`typescript`、`vite` 和 `vite-plugin-vue-setup-extend` 依赖项。

**2. 路由配置更新**:

*   移除了 `/Map` 路由。
*   移除了 `Live` 组件。
*   添加了 `AIdemo` 组件。

**3. 页面更新**:

*   **App.vue**: 移除了大会直播链接。
*   **Guide.vue**: 移除了顶部背景模块。
*   **news.vue**: 
    *   移除了新闻列表的样式和分页组件。
    *   添加了新闻标题和新闻列表的样式。
    *   修改了新闻数据获取逻辑。

**4. 其他更改**:

*   在 `main.ts` 中移除了 `@iconify/vue` 的导入和使用。
*   在 `src/router/index.ts` 中移除了 `/Map` 路由。
*   在 `src/views/Map.vue` 中移除了地图组件和路线规划功能。

## 总结

这次代码更新主要移除了与地图和直播相关的功能，并添加了新的组件和路由。同时，也更新了依赖项和页面样式。