# ArkGlide

**一个代码优先、全前端运行的 3D 游戏引擎。**

ArkGlide 想把游戏开发里尽可能多的事情放进浏览器：编辑场景、写逻辑、预览、调试，再到最后发布。

用户使用 JavaScript 编写游戏逻辑，编辑器和 SDK 主要使用 TypeScript，核心运行时由 C++ 编写，并通过 Emscripten 编译为 WebAssembly。3D 视口基于 Babylon.js，优先使用 WebGPU，并保留 WebGL2 回退。

我们做 ArkGlide，并不是想把游戏开发变成一堆按钮和面板。代码仍然是核心，编辑器负责把场景、资源和调试这些事情做得更顺手。

打开浏览器，就可以开始做游戏。

---

## 我们的项目

- [`arkglide`](https://github.com/arkglide/arkglide) — 前端编辑器、SDK 和运行时。
- [`relay`](https://github.com/arkglide/arkglide-relay) — 使用 Go 编写的联机中继服务器模板，采用 BYOS 模式。

项目目前还处在早期开发阶段。编辑器、SDK、运行时和协议都还在继续调整，仓库之间的结构也可能随着开发推进发生变化。

---

## 技术方向

ArkGlide 的编辑器使用 **React + Vite + TypeScript + Material Design 3**，代码编辑基于 Monaco。

3D 视口使用 **Babylon.js**，以 WebGPU 为主要渲染路径，同时保留 WebGL2 兼容方案。

引擎底层使用 **C++ → Emscripten → WebAssembly**，用户脚本则使用 **JavaScript ESM**。

发布后的游戏由普通的 HTML、JavaScript 和 WASM 组成，不依赖 ArkGlide 的官方运行环境，可以直接部署到常见的静态托管服务。

联机部分使用 **WebSocket**。我们提供协议、客户端适配以及开源的 Go 中继服务器模板，但不提供必须依赖的官方托管服务器。

---

## 核心理念

**代码优先。** ArkGlide 面向愿意写代码的开发者。图形化工具可以帮你创建场景、配置组件和处理重复工作，但它们不应该把真正的游戏逻辑藏起来。对于能够通过界面完成的操作，我们希望尽可能提供对应代码或等效 JavaScript 的查看方式。

**全前端。** 编辑器、预览、调试和导出都尽量在浏览器中完成。开发 ArkGlide 项目不应该以安装大型桌面软件或配置复杂本地环境为前提。

**BYOS 联机。** ArkGlide 不打算把游戏锁在某个官方服务器平台上。我们定义联机协议并提供参考实现，开发者可以自行部署服务器，也可以基于协议实现自己的后端。

---

## 参与贡献

ArkGlide 还很早，所以现在也是比较适合参与的时候。

如果你对 Web 3D、游戏引擎、C++ / WebAssembly、编辑器开发或者浏览器里的开发工具感兴趣，欢迎直接参与。

发现问题可以提交 Issue；有新的实现、修复或文档改进，可以提交 Pull Request。对于涉及运行时、SDK API、协议或较大架构调整的改动，建议先开 Issue 讨论一下方向。

开发文档、协议和架构说明可以在 [`docs`](https://github.com/arkglide/docs) 中查看。

如果仓库中已经提供贡献指南，也请在提交代码前先阅读对应的 `CONTRIBUTING.md`。

---

**Code first. Frontend only. Bring your own server.**

ArkGlide 还没有完成。

很多东西可能会改，也有很多东西还没做——但这正是现在参与它比较有意思的地方。
