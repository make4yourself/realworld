# ![RealWorld Example Applications](media/realworld.png)

### 保持前沿 — [加入我们的 Gitter !](https://gitter.im/realworld-dev/main) 🎉

[![Travis](https://img.shields.io/travis/gothinkster/realworld.svg)](https://travis-ci.org/gothinkster/realworld) [![Gitter](https://img.shields.io/gitter/room/realworld-dev/main.svg)](https://gitter.im/realworld-dev/main) [![Twitter](https://img.shields.io/twitter/follow/gothinkster.svg?style=social&label=Follow)](https://twitter.com/gothinkster)

<p align="center">
<img src="media/stacks_hr.gif"  />
</p>

<a href="https://demo.realworld.io/"><img src="media/ conduit_l.png" align="right" width="250px" /></a>

### 了解我们是如何用 [前端](#frontends) 和  [后端](#backends) 搭建的一个 *完全相同的* Medium.com 克隆 (称作为 [Conduit](https://demo.realworld.io))。 是的, 你可以任意混合匹配前后两端, 因为 **他们都符合相同的 [API 规范](spec/)** 😮😎

虽然大多数「待办事项」演示提供了对框架功能的粗略浏览，但它们通常不会传达实际使用框架构建 **真实** 应用程序所需的知识视角。

RealWorld 通过允许您选择任意前端（React， Angular 2 等等）和任意后端（Node， Django 等等）来解决此类问题，并了解他们如何在真实世界开发场景中为设计精美的全栈应用程序「Conduit」提供动力。

*阅读 [完整的 RealWorld 博客文章](https://medium.com/@ericsimons/introducing-realworld-6016654d36b5)*


# 前端
<!-- INSERT_FRONTEND_REPOS -->

正在进行当中：
<!--INSERT_FRONTEND_WIP -->

# 后端
<!-- INSERT_BACKEND_REPOS -->

正在进行当中：
<!-- INSERT_BACKEND_WIP -->

# 移动端
<!-- INSERT_MOBILE_REPOS -->

正在进行当中：
<!-- INSERT_MOBILE_WIP -->

# 全栈

**由于这些的实现采用了全栈开发，但它们仍遵循相同的功能和 UX 规范**

仍在开发当中: **[Meteor]() | [Ruby Hyperloop]() | [Firebase](https://github.com/gothinkster/realworld/issues/199)**

# 创建一个新的技术栈

[![创建一个新的技术栈](media/upcoming_stacks.png)](/spec)

### 知道其中任何一个框架（或未列出的框架）吗？<br />[**Create a new framework implementation >>>**](/spec)

或者你可以 [查看即将到来的堆栈 (正在进行当中)](https://github.com/gothinkster/realworld/issues?q=is%3Aopen+is%3Aissue+label%3Awip)

注意: 所有作为正在 WIP 的技术栈都是实验性的，并不完整。

不要指望一切都能开箱即用！

<br />

# 我是如何准备一切 & 运行的?

只需按照任何前端 和/或 后端仓库的 README 中有关准备启动和运行的说明进行操作就行了。

### 您能教我如何从头开始构建每个技术栈吗？

对！我们已经为所有技术栈构建了分步教程，教您如何从 `git init` 一直到生产就绪应用程序. [**立即开始学习 >>>**](https://thinkster.io/tutorials/fullstack)

<br />

# 社区创建的资源

基于 RealWorld 项目的 Fork，教程，讲习班和其他资源：

- [**React+Redux / Node testing workshop**](https://github.com/kentcdodds/testing-workshop) by [**Kent C. Dodds**](https://github.com/kentcdodds)
  - 示例仓库显示了使用 TDD 一起工作的 React + Redux 和 Node 技术栈
  - 这是他的工作室录制的 [**YouTube 视频**](https://www.youtube.com/watch?v=DdqiXcYDv-8)
- [**RealWorld React/NodeJS E2E Tests**](https://github.com/anishkny/realworld-e2e-test) by [**Anish Karandikar**](https://github.com/anishkny)
  - 一个显示如何将 [React](https://github.com/gothinkster/react-redux-realworld-example-app) 前端与 [NodeJS](https://github.com/gothinkster/node-express-realworld-example-app) 后端连接以实现 RealWorld 的全栈仓库
  - 包括使用 [Chrome Puppeteer](https://github.com/GoogleChrome/puppeteer) 和 [Mocha](https://mochajs.org) 并与 [Travis CI](https://travis-ci.org/anishkny/realworld-e2e-test) 和 [CircleCI](https://circleci.com/gh/anishkny/realworld-e2e-test) 等 CI 系统配合使用 E2E 集成测试
  - 还演示了如何使用 [Greenkeeper](https://greenkeeper.io) 进行自动依赖性更新，以及如何使用 [Snyk](https://snyk.io/) 进行漏洞监视。
- 性能比较:
  - [A Real-World Comparison of Front-End Frameworks with Benchmarks 2019](https://medium.freecodecamp.org/a-realworld-comparison-of-front-end-frameworks-with-benchmarks-2019-update-4be0d3c78075)
  - [A Real-World Comparison of Front-End Frameworks with Benchmarks 2018](https://medium.freecodecamp.org/a-real-world-comparison-of-front-end-frameworks-with-benchmarks-2018-update-e5760fb4a962)
  - [A Real-World Comparison of Front-End Frameworks with Benchmarks 2017](https://medium.freecodecamp.org/a-real-world-comparison-of-front-end-frameworks-with-benchmarks-e1cb62fd526c)

<br />

# 更多学习

- ["介绍 RealWorld 🙌"](https://medium.com/@ericsimons/introducing-realworld-6016654d36b5) by Eric Simons
- 每个教程均基于相同的 [API spec](api/) 规范构建，以确保每个前端和后端的模块化
- 每个前端都使用相同手工制作的 [Bootstrap 4 主题](https://github.com/gothinkster/conduit-bootstrap-template) 来实现相同的 UI/UX
- 后端 API 的托管版本可供公共使用，不需要 API 密钥
- 有兴趣创建一个新的 RealWorld 技术栈吗？查看我们的 [开始指南 & 规格](/spec)

<br />


# 创建者们

没有 [开源社区](#special-thanks-to) 的持续帮助，就没法实现 RealWorld。此外，我们还有一个核心项目团队，由以下人员组成：

#### [Anish Karandikar](https://github.com/anishkny) - 核心维护者

<img align="left" width="40" height="40" src="https://avatars1.githubusercontent.com/u/357499?v=3&s=100">

MathWorker, ex-Google, ex-Computational Fluid Dynamicist, forever lover of tech & humanities ❤️

#### [Cameron Chapman](https://github.com/Cameron-C-Chapman) - 核心维护者

<img align="left" width="40" height="40" src="https://avatars1.githubusercontent.com/u/1323581?v=3&s=100">

Cameron Chapman is a Software Engineer at FanThreeSixty. He's an open source enthusiast and is helping to teach a local web development boot camp at Kansas University.

#### [Eric Simons](https://twitter.com/ericsimons40) - 创始人/维护者

<img align="left" width="40" height="40" src="https://avatars1.githubusercontent.com/u/556934?v=3&s=100">

Eric is a Software Engineer, UI Designer, and author of many technical books & tutorials. He oversees the project direction, maintenance and organizes the planning and development efforts of the team.

#### [Albert Pai](https://twitter.com/iamalbertpai) - 创始人/维护者

<img align="left" width="40" height="40" src="https://avatars0.githubusercontent.com/u/1776432?v=3&s=100">

Albert is a Software Engineer, DevOps ninja, and author of many technical books & tutorials. He oversees the project direction, maintenance and organizes the planning and development efforts of the team.

#### [Thinkster](https://twitter.com/gothinkster) - 资金/支持

<img align="left" width="40" height="40" src="https://avatars0.githubusercontent.com/u/8601733?v=3&s=100">

[Thinkster](https://thinkster.io) creates high quality resources that help Javascript developers succeed. The RealWorld project wouldn't exist without their funding, so please consider investing in [a Pro subscription](https://thinkster.io/pro) to help support us!


#### [James Brewer](https://twitter.com/brwr_) - 管理员

<img align="left" width="40" height="40" src="https://avatars1.githubusercontent.com/u/4095660?v=3&s=100">

James is a Software Engineer at Square and a contributor to the Django project. He created & maintains the RW Django codebase and continually provides guidance for the RealWorld project itself.

#### [Sandeesh S.](https://github.com/SandeeshS) - 管理员

<img align="left" width="40" height="40" src="https://avatars1.githubusercontent.com/u/16877877?v=3&s=100">

Full stack developer, Laravel enthusiast, Digital marketing specialist and an avid gamer.




## 特别鸣谢

如果没有开源社区的审查代码库和创建新的应用程序实现以及许多其他有助于推动该项目前进的任务的帮助 RealWorld 将无法实现。我们特别感谢为 RealWorld 做出贡献的 OSS 领导人：

- **Dan Abramov** (Redux 创建者) 帮助 [激发了最初的想法](https://twitter.com/dan_abramov/status/692009757775896577), [使 Redux 社区参与其中](https://github.com/reactjs/redux/issues/1353), 并慷慨地花实践提供有关 Redux 代码库的反馈
- **Max Lynch** (Ionic 创建者) 在这个项目的初期花时间提供了指导
- **Addy Osmani** (TodoMVC 创建者) 帮助 [激发了最初的想法](https://twitter.com/addyosmani/status/762828483433144320) 以及他对 TodoMVC 相关项目的出色贡献
- **TodoMVC** ([团队 & 贡献者](https://github.com/tastejs/todomvc#team)) 杰出和成功的贡献；他们的项目和组织对于我们来说是一个非常宝贵的类比，因为我们以及建立了 RealWorld
- **James Brewer** (Django 文档贡献者) 进行了无数次头脑风暴会议，帮助命名了该项目，并创建了 Django 代码库和教程




# License
All of the codebases are **MIT licensed** unless otherwise specified.

<br />

[![由 Thinkster 为你呈现](media/end.png)](https://thinkster.io)
