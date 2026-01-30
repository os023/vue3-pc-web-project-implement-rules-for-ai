# B-01 推荐使用的 npm 库（联邦项目）

联邦项目（pnpm + lerna）下，各应用与共享包可**分别**声明依赖；推荐在根或各 package 内统一使用共用约定中的库。

| 用途 | 推荐库 | 说明 |
|------|--------|------|
| 包管理 / workspace | pnpm | 根与各 package 统一使用 pnpm；配合 pnpm-workspace.yaml |
| 多包编排 / 发布 | lerna | 多包版本与发布编排，与 pnpm 配合使用 |

- 共享库（如 `packages/shared-ui`、`packages/shared-utils`）可把 dayjs、lodash-es 等声明为 dependency 或 peerDependency；各 app 通过 workspace 引用共享包，避免重复打包。
- 新增通用能力时优先在共用范围内选型；若引入新库，需在根或共享包文档中补充说明。

其余见 [shared/01-推荐使用的npm库.md](../shared/01-推荐使用的npm库.md)。
