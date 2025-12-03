# VCC 3

VCC (Vue Component Creator) 是一个低代码平台中的独立 Vue 组件代码编辑器，可以独立运行。当前版本是基于 Vue3 的 VCC 3 版本。

**通过拖拽式操作，快速完成 Vue 组件代码骨架的搭建，提升开发效率。**

> 🌐 **在线预览**: [https://vcc3.vercel.app/](https://vcc3.vercel.app/)  
> 📦 **当前版本**: Vue3 + Vite  
> 📚 **使用示例**: [https://github.com/sahadev/vcc3-use-demo](https://github.com/sahadev/vcc3-use-demo)

## ✨ 特性

- 🎨 **可视化拖拽** - 通过拖拽快速搭建组件结构
- ⚡ **实时预览** - 代码生成实时预览，所见即所得
- 📝 **代码生成** - 自动生成规范的 Vue 组件代码
- 🎯 **多组件库支持** - 支持 Element Plus、Ant Design Vue、Vant、iView、Quasar 等主流组件库
- 🔧 **属性编辑** - 可视化编辑组件属性，支持扩展
- 📦 **模板预设** - 提供常用组件模板，快速开始
- 🎨 **代码编辑** - 支持二次编辑 Vue 代码和 JS 逻辑
- 📊 **结构视图** - 可视化查看组件结构关系
- 💾 **导出功能** - 支持导出单页 HTML 和 Vue 组件代码

## 🚀 快速开始

### 环境要求

- Node.js >= 14.x
- npm >= 6.x 或 yarn >= 1.x

### 安装依赖

```bash
npm install
# 或
yarn install
```

### 启动开发服务器

```bash
npm run dev
# 或
npm run serve
```

启动成功后，访问 [http://localhost:9818/](http://localhost:9818/) 即可预览。

### 构建生产版本

```bash
# 构建为库文件
npm run build

# 构建为 Vercel 部署版本
npm run build:vercel

# 构建为发布版本
npm run build:release
```

## 🛠️ 技术栈

- **框架**: Vue 3.3+
- **构建工具**: Vite 2.6+
- **UI 组件库**: Element Plus 2.4+
- **状态管理**: Vuex 4.0+
- **拖拽功能**: vuedraggable 4.1+
- **代码编辑器**: CodeMirror
- **图表库**: ECharts 5.4+

## 📚 支持的组件库

VCC 3 目前支持以下主流 Vue 组件库：

- ✅ **Element Plus** - 基于 Vue 3 的组件库
- ✅ **Ant Design Vue** - 企业级 UI 设计语言
- ✅ **Vant** - 轻量、可靠的移动端组件库
- ✅ **iView** - 高质量 UI 组件库
- ✅ **Quasar** - 高性能 Vue.js 框架
- ✅ **原生 HTML** - 支持原生 HTML 元素

## 📁 项目结构

```
vue-component-creater-ui/
├── src/
│   ├── components/          # 核心组件
│   │   ├── AttributeInput.vue    # 属性输入组件
│   │   ├── Code.vue              # 代码展示组件
│   │   ├── CodeEditor.vue       # 代码编辑器
│   │   ├── CodeStructure.vue    # 代码结构视图
│   │   ├── Preview.vue          # 预览组件
│   │   └── RawComponents.vue    # 原始组件列表
│   ├── components-v2/        # V2 版本组件
│   │   ├── VCC.vue              # 主组件
│   │   └── ToolsBar.vue         # 工具栏
│   ├── rawComponents/        # 组件库源文件
│   │   ├── element/             # Element Plus 组件
│   │   ├── antd/                # Ant Design Vue 组件
│   │   ├── vant/                # Vant 组件
│   │   ├── iview/               # iView 组件
│   │   ├── quasar/              # Quasar 组件
│   │   └── raw/                 # 原生 HTML 组件
│   ├── libs/                 # 核心库文件
│   │   ├── store.js             # 状态管理
│   │   ├── code-generator-factory.js  # 代码生成工厂
│   │   └── ...
│   ├── map/                  # 组件映射文件
│   ├── utils/                # 工具函数
│   └── main.js               # 入口文件
├── public/                   # 静态资源
├── dist/                     # 构建输出
├── vite.config.js           # Vite 配置
└── package.json             # 项目配置
```

## 📖 使用指南

### 基本使用

1. **拖拽组件** - 从左侧组件库中拖拽组件到中间预览区域
2. **编辑属性** - 点击组件，在右侧属性面板中编辑组件属性
3. **查看代码** - 点击右上角代码图标，查看实时生成的代码
4. **导出代码** - 复制生成的代码到你的项目中

### 视频教程

- [【拖拽式Vue组件代码生成平台(LCG)介绍视频】](https://www.bilibili.com/video/BV17h411f7g2/)

### 详细文档

📚 **完整文档**: [https://vcc3-docs.surge.sh/#/](https://vcc3-docs.surge.sh/#/)

## 🔧 开发指南

### 添加新组件库

1. 在 `src/rawComponents` 目录下创建以组件库名称命名的文件夹（如 `myui`）
2. 在该文件夹内创建 `index.vue` 文件，并引入组件
3. 在组件元素上添加 `lc-mark` 属性，使其可被拖拽
4. 在 `src/components/RawComponents.vue` 中引入新组件库
5. 执行编译命令：`npm run compileComponent`

### 组件标记

组件必须添加 `lc-mark` 属性才能被拖拽：

```vue
<el-button lc-mark>默认按钮</el-button>
```

### 编译组件

添加或修改组件后，需要重新编译：

```bash
npm run compileComponent
```

### 注意事项

- ⚠️ 在 `script` 标签内部慎用大于小于号，可能导致预编译阶段解析出错
- ⚠️ 组件的 CSS 中不能使用 SCSS 写法，否则编译 Vue 文件会不通过
- ⚠️ 在文件中不能声明与 prop 相同的变量名

## 📝 更新日志

### v0.5.3 (当前版本)

- ✅ 升级至 Vue 3.3+
- ✅ 升级至 Vite 2.6+
- ✅ 更新 Element Plus 组件库版本
- ✅ 支持生成单页 HTML
- ✅ 支持 Vue2 和 Vue3 代码生成
- ✅ 优化代码生成逻辑
- ✅ 改进用户体验

### 历史版本

- **2023-12-06**: 更新 Element 组件库版本、更新 Vue 框架版本
- **2022-03-16**: 支持生成单页 Html，支持 Vue2 以及 Vue3，并支持一键部署至 VCC 服务器

## 🔗 相关项目

### 核心依赖

VCC 依赖于核心代码转换库：[vue-component-code-creater](https://github.com/sahadev/vue-component-code-creater)

该库负责：
- Vue 文件的解析
- Vue 文件的生成
- 代码结构转换

如需修改核心实现，请参考该库的源码。

## ❓ 常见问题

### Q: 如何添加自定义组件？

A: 参考 [开发指南](#-开发指南) 中的"添加新组件库"部分。

### Q: 为什么拖拽的组件无法显示？

A: 确保组件元素已添加 `lc-mark` 属性，并且已执行 `npm run compileComponent` 重新编译。

### Q: 生成的代码可以直接使用吗？

A: 生成的代码是标准的 Vue 组件代码，可以直接在项目中使用。但建议根据实际需求进行微调。

### Q: 支持哪些 Vue 版本？

A: 当前版本支持 Vue 3.x，历史版本支持 Vue 2.x。

### Q: 如何部署到生产环境？

A: 执行 `npm run build` 构建项目，然后将 `dist` 目录部署到静态服务器即可。

## 🤝 贡献指南

我们欢迎所有形式的贡献！

### 贡献流程

1. Fork 本仓库
2. 创建特性分支 (`git checkout -b feature/AmazingFeature`)
3. 提交你的修改 (`git commit -m 'Add some AmazingFeature'`)
4. 推送到分支 (`git push origin feature/AmazingFeature`)
5. 开启一个 Pull Request

### 贡献方向

- 🐛 修复 Bug
- ✨ 添加新功能
- 📝 完善文档
- 🎨 优化 UI/UX
- ⚡ 性能优化
- 🔧 添加新的组件库支持

## 📮 反馈与支持

### 问题反馈

如有建议或发现问题，欢迎在 [GitHub Issues](https://github.com/sahadev/vue-component-creater-ui/issues) 中反馈。

### 联系方式

- 📧 **邮箱**: sahadev@foxmail.com
- 💬 **微信**: SAHADEV-smile（加好友时请备注 VCC）
- 👥 **交流群**: 添加微信后，我会拉你入群和大家一起讨论

### 项目愿景

这个项目目前主要面向前端开发者，帮助提升开发效率。未来计划：
- 🎯 面向后端开发者
- 🎯 面向产品和 UE 设计师
- 🎯 提供更多组件库支持
- 🎯 增强代码生成能力

我们特别希望可以和大家一起完善这个项目！🚀

## 📄 开源协议

本项目遵循 [MIT 协议](http://www.opensource.org/licenses/MIT)

---

<div align="center">

**如果这个项目对你有帮助，请给一个 ⭐ Star 支持一下！**

Made with ❤️ by [sahadev](https://github.com/sahadev)

</div>
