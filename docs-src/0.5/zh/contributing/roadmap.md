# 路线图和功能集

此功能集和路线图可以帮助您确定 Dioxus 目前的功能是否适合您的需求。

如果您需要的功能尚不存在，或者您想要为路线图上的项目做出贡献，请随时通过[加入 Discord](https://discord.gg/XgGxMSkvUM)参与进来。

一般来说，以下是每个平台的状态：

- **Web**：Dioxus 是纯 Web 应用的绝佳选择，特别是对于 CRUD/复杂应用程序。但是，它缺少 React 的生态系统，因此您可能会缺少一些组件库或一些有用的 Hook。

- **SSR**：Dioxus 是预渲染、水合和在 Web 端点上呈现 HTML 的绝佳选择。但要注意，虚拟 DOM 目前不是 `Send + Sync`。

- **Desktop**：您现在可以构建非常有竞争力的单窗口桌面应用程序。但是，多窗口应用程序需要来自 Dioxus 核心的支持，目前尚未准备好。

- **Mobile**：移动支持还很年轻。您将边学边摸索，而且没有多少支持外设的支持包。

- **LiveView**：LiveView 支持还很年轻。您将边学边摸索。值得庆幸的是，没有一项工作是太难的，任何工作都可以上游到 Dioxus。

## 功能

---

| 功能                      | 状态   | 描述                                                         |
|---------------------------|--------|---------------------------------------------------------------|
| 条件渲染                  | x      | if/then 隐藏/显示组件                                         |
| Map, Iterator             | x      | map/filter/reduce 生成 rsx!                                    |
| Keyed 组件                | x      | 使用键进行高级差异                                            |
| Web                       | x      | 用于 Web 浏览器的渲染器                                        |
| Desktop (webview)         | x      | 用于桌面的渲染器                                               |
| 共享状态 (Context)        | x      | 通过树共享状态                                                 |
| Hooks                     | x      | 组件中的内存单元                                               |
| SSR                       | x      | 直接呈现为字符串                                               |
| 组件子节点                | x      | cx.children() 作为节点列表                                     |
| 无头组件                  | x      | 不返回实际元素的组件                                           |
| 片段                      | x      | 没有真实根的多个元素                                           |
| 手动 Props                | x      | 使用展开语法手动传递 props                                     |
| 受控输入                  | x      | 围绕输入的有状态包装器                                         |
| CSS/Inline 样式           | x      | 内联样式/属性组的语法                                         |
| 自定义元素                | x      | 定义新的元素原语                                               |
| Suspense                  | x      | 从未来/承诺安排未来呈现                                      |
| 集成错误处理              | x      | 使用？语法优雅地处理错误                                      |
| NodeRef                   | x      | 直接访问节点                                                   |
| 重新水合                  | x      | 预先呈现为 HTML 以加快首次内容呈现速度                          |
| 无卡顿渲染                | x      | 大型差异在帧之间分段，实现丝般顺滑的过渡                       |
| Effects                   | x      | 在组件提交到呈现后运行效果                                     |
| 门户                      | *      | 在传统树结构之外呈现节点                                       |
| 合作调度                  | *      | 将重要事件优先于不重要事件                                    |
| 服务器组件                | *      | 用于 SPA 和服务器的混合组件                                    |
| 捆绑拆分                  | i      | 高效异步加载应用程序                                           |
| 懒加载组件                | i      | 随着页面加载动态加载新组件                                     |
| 一流全局状态              | x      | redux/recoil/mobx 在 context 之上                               |
| 原生运行                  | x      | 作为便携式二进制运行，无需运行时 (Node)                        |
| 子树记忆                  | x      | 跳过静态元素子树的差异                                         |
| 高效模板                  | x      | rsx! 调用在 DOM 端被转换为模板                                 |
| 编译时正确性              | x      | 在无效模板布局时抛出错误                                       |
| 启发式引擎                | x      | 跟踪组件内存使用情况以最小化未来分配                           |
| 细粒度反应                | i      | 对于细粒度更新跳过差异检查                                     |

- x = 实现并且可用
- \* = 正在积极开发中
- i = 尚未实现或正在开发中

## 路线图

以下功能计划在未来的 Dioxus 中实现：

### 核心

- [x] 发布 Dioxus 核心
- [x] 更新文档以包含更多理论知识，并更加全面
- [x] 支持 HTML-side 模板以实现极快的 DOM 操作
- [ ] 支持相同虚拟 DOM 的多个渲染器（子树）
- [ ] 支持 ThreadSafe (Send + Sync)
- [ ] 支持 Portals

### SSR

- [x] SSR 支持 + 水合
- [x] 集成 suspense 对 SSR 的支持

### 桌面

- [ ] 声明式窗口管理
- [ ] 用于构建/打包的模板
- [ ] 本地访问 Canvas/WebGL 上下文

### 移动

- [ ] 移动标准库
  - [ ] GPS
  - [ ] 相机
  - [ ] 文件系统
  - [ ] 生物识别
  - [ ] WiFi
  - [ ] 蓝牙
  - [ ] 通知
  - [ ] 剪贴板
- [ ] 动画

### 捆绑 (CLI)

- [x] 从 HTML 转换为 RSX
- [x] Dev 服务器
- [x] 实时重新加载
- [x] 从 JSX 转换为 RSX
- [ ] 热模块替换
- [ ] 代码拆分
- [x] 资源宏
- [x] CSS 管道
- [x] 图像管道

### 基本 Hook

- [x] 路由器
- [x] 全局状态管理
- [ ] 调整大小观察器

## 进行中的工作

### 构建工具

我们目前正在开发我们自己的构建工具，称为 [Dioxus CLI](https://github.com/DioxusLabs/dioxus/tree/main/packages/cli)，它将支持：

- 交互式 TUI
- 实时重新配置
- 热 CSS 重新加载
- 浏览器和源代码之间的双向数据绑定
- `rsx!` 的解释器
- 发布到 github/netlify/vercel
- iOS/Desktop 等的打包

### 服务器组件支持

尽管目前尚未完全实现，但预期 LiveView 应用程序可以是 Wasm 和服务器呈现之间的混合，其中仅页面的部分是“实时的”，页面的其余部分要么是服务器呈现的，要么是静态生成的，或者由主机 SPA 处理。

### 本地渲染

我们目前正在开发一个使用 WGPU 的 Dioxus 本地渲染器，称为 [Blitz](https://github.com/DioxusLabs/blitz/)。这将允许您构建可以在 iOS、Android 和桌面上本地呈现的应用程序。
