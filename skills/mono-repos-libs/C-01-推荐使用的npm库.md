# C-01 推荐使用的 npm 库（联邦库）

联邦库（pnpm + lerna）下，各**库包**以发布产物为主；推荐在库内统一使用共用约定中的库，便于与使用方（主应用）一致。

| 用途 | 推荐库 | 说明 |
|------|--------|------|
| 包管理 / workspace | pnpm | 根与各库包统一使用 pnpm；配合 pnpm-workspace.yaml |
| 多包编排 / 发布 | lerna | 多包版本与发布编排，与 pnpm 配合使用 |

- 库包将 dayjs、lodash-es 等声明为 dependency 或 peerDependency，按发布策略选择；产物为 ESM（及可选 CJS），供主应用按需引入。
- 新增通用能力时优先在共用范围内选型；若引入新库，需在库 README 或本约定中补充说明。

其余见 [shared/01-推荐使用的npm库.md](../shared/01-推荐使用的npm库.md)。
