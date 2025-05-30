从提供的代码片段中，我们可以看到以下更改：

**src/App.vue**:

* 添加了新的导航链接 `/AI`，用于访问 AI 智能体页面。

**src/components/Login.vue**:

* 添加了快速登录按钮，用于快速登录评委或 HR。
* 快速登录功能需要用户先同意服务条款和隐私政策。

**src/views/Guest.vue**:

* 移除了嘉宾视频链接的显示。

**src/views/Guide.vue**:

* 在导航栏中添加了新的链接，用于访问大会餐饮和联系我们页面。

**src/views/Home.vue**:

* 在大会议程日期列表中添加了点击事件，用于跳转到相应的议程页面。
* 在新闻列表中添加了点击事件，用于跳转到相应的新闻详情页面。

**src/views/Live.vue**:

* 修改了推荐内容列表中的图片链接。

**src/views/news.vue**:

* 在新闻列表中添加了点击事件，用于跳转到相应的新闻详情页面。

**总结**:

这些更改主要涉及添加新的功能（如快速登录和 AI 智能体页面）和改进用户体验（如日期点击跳转和新闻点击跳转）。此外，还移除了一些不再需要的功能（如嘉宾视频链接）。