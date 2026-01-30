# B-01 推荐使用的 npm 库（联邦项目）

联邦项目（pnpm + lerna）下，各应用与共享包可**分别**声明依赖；推荐在根或各 package 内统一使用以下库，避免多套同类库并存。

| 用途 | 推荐库 | 说明 |
|------|--------|------|
| 包管理 / workspace | pnpm | 根与各 package 统一使用 pnpm；配合 pnpm-workspace.yaml |
| 多包编排 / 发布 | lerna | 多包版本与发布编排，与 pnpm 配合使用 |
| 时间处理 | dayjs | 日期格式化、解析、计算；禁止手写日期逻辑。详见 [B-06-时间处理.md](B-06-时间处理.md) |
| 数组/对象/判断 | lodash-es | 按需引入，减少打包体积。详见 [B-07-数组对象判断.md](B-07-数组对象判断.md) |
| 状态管理 | Pinia | 各 app 独立使用。详见 [B-05-状态管理.md](B-05-状态管理.md) |
| 路由 | Vue Router | 与 Vue3 配套，各 app 独立配置 |
| HTTP | axios 或项目约定 | 各 app 的拦截器统一处理公共错误 |
| 图标 | @iconify/vue 或 Iconify 生态 | 与 [B-10-样式规范](B-10-样式规范.md) 中的资源约定一致 |
| 工具/校验等 | 按需选型 | 优先 lodash-es；共享能力放 `packages/shared-utils`，避免各 app 重复安装 |

- 共享库（如 `packages/shared-ui`、`packages/shared-utils`）可把 dayjs、lodash-es 等声明为 dependency 或 peerDependency；各 app 通过 workspace 引用共享包，避免重复打包。
- 新增通用能力时优先在以上范围内选型；若引入新库，需在根或共享包文档中补充说明。

共用规则见 [shared/01-推荐使用的npm库.md](../shared/01-推荐使用的npm库.md)。
