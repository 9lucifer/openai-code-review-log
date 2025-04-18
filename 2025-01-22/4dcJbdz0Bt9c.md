### 代码主要改动

#### src/main.ts
1. **导入 ElementPlusIconsVue**: 新增了对 `@element-plus/icons-vue` 的导入，这表明代码中可能使用了 Element Plus 图标组件。
2. **注册图标组件**: 通过一个循环，将 Element Plus 的图标组件注册到 Vue 应用实例中。这是为了在模板中使用图标。

#### src/views/Guest.vue
1. **模板改动**: 
   - 添加了新的 HTML 结构，包括标题、专家委员会和大会嘉宾的展示。
   - 使用了 Element Plus 的图标组件 `VideoPlay`。
   - 添加了鼠标悬停显示嘉宾详细信息的交互。
   - 添加了嘉宾过滤功能。

2. **脚本改动**: 
   - 添加了专家委员会和大会嘉宾的数据。
   - 添加了控制专家委员会和大会嘉宾显示的逻辑。
   - 添加了过滤嘉宾的逻辑。

3. **样式改动**: 
   - 修改了 `.guest_title` 的样式，使其居中显示。
   - 添加了背景图片和背景色渐变。
   - 修改了 `.expert-title` 的样式，使其具有渐变背景。
   - 添加了 `.arrow-left` 和 `.arrow-right` 的样式，用于控制专家委员会的左右滑动。
   - 添加了 `.guest-item` 的样式，用于显示嘉宾信息。

### 新提交代码作用

1. **src/main.ts**
   - 注册图标组件，方便在模板中使用图标。

2. **src/views/Guest.vue**
   - 展示专家委员会和大会嘉宾信息。
   - 实现嘉宾过滤功能。
   - 实现鼠标悬停显示嘉宾详细信息。

### 代码缺陷

1. **src/main.ts**
   - 注册图标组件时，没有对组件进行校验，可能会出现注册失败的情况。

2. **src/views/Guest.vue**
   - 专家委员会和大会嘉宾的图片路径可能存在错误，导致无法正常显示。
   - 嘉宾过滤功能可能存在性能问题，当嘉宾数量较多时，过滤操作可能会较慢。
   - 鼠标悬停显示嘉宾详细信息时，样式可能需要进一步优化。

3. **样式**
   - 部分样式可能存在重复，需要进行整理。
   - 部分样式可能需要根据实际需求进行调整。