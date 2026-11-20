# omds-chat.github.io

omds-chat 组织的 Pages 入口仓库。仓库内容全部是静态文件,由 GitHub Pages 直接托管根目录,不经过任何构建流程。

组织的定位与仓库组成以 [.github 仓库的中文说明](https://github.com/omds-chat/.github/blob/main/profile/README.md) 与 [英文说明](https://github.com/omds-chat/.github/blob/main/profile/README.en-US.md) 为准,本仓库不重复陈述。组织的主产品为 DeepSeek-Chat-Enhanced:代码在 [该仓库](https://github.com/omds-chat/DeepSeek-Chat-Enhanced),在线页面通过 Pages 提供,统一由本仓库的 [`chat/`](./chat/) 入口进入。

## 目录结构

```text
.
├── index.html        组织入口页,列出组织对外的各个入口
├── chat/
│   └── index.html    在线聊天入口,跳转到 DeepSeek-Chat-Enhanced 的 Pages 页面
├── .nojekyll         空文件,关闭 GitHub Pages 的 Jekyll 处理,文件按原样发布
├── .gitignore        忽略规则,排除依赖目录、日志、临时目录与本地 Agent 配置(AGENTS.md、.agent/、.agents/)
├── LICENSE           Apache License 2.0 全文
└── README.md         本说明文件
```

## chat/ 的跳转用途

`chat/index.html` 是纯静态跳转页,跳转目标固定为:

```text
https://omds-chat.github.io/DeepSeek-Chat-Enhanced/
```

跳转由两条路径完成:

- `<meta http-equiv="refresh" content="0; url=...">`,作为无脚本环境下的兜底。
- 一段内联脚本执行 `location.replace()`,脚本可用时优先跳转,且不向浏览器历史记录写入多余条目。

页面正文保留说明文字与可点击的备用链接;目标站点不可达时,用户也可以前往产品仓库页,从 Releases 获取离线包。该页面不做任何可达性探测,也不引入任何外部资源,样式与脚本全部内联。

## 部署与本地预览

在仓库的 Pages 设置中把发布源指向默认分支的根目录(`/`),无需构建步骤与额外产物。`.nojekyll` 的存在确保文件按原样发布,不经过 Jekyll 处理。

本地预览用任意静态服务器托管仓库根目录即可:首页为 `index.html`,跳转页为 `chat/index.html`。

## 许可

本项目以 Apache License 2.0 授权,全文见 [LICENSE](./LICENSE)。
