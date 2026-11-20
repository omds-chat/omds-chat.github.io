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

跳转只有一条路径:

- `<meta http-equiv="refresh" content="0;url=https://omds-chat.github.io/DeepSeek-Chat-Enhanced/">`:浏览器解析到页面即刻跳转,无需等待,也不依赖脚本。

页面正文只保留失败提示与指向同一目标的手动链接(`target="_self"`),中英各一行,仅在自动跳转未生效或目标地址不可达时使用。页面声明 `lang="en"` 与 `charset=utf-8`,不含 `<script>`、不含内联样式与任何外部资源,也不做可达性探测。

## 部署与本地预览

在仓库的 Pages 设置中把发布源指向默认分支的根目录(`/`),无需构建步骤与额外产物。`.nojekyll` 的存在确保文件按原样发布,不经过 Jekyll 处理。

本地预览用任意静态服务器托管仓库根目录即可:首页为 `index.html`,跳转页为 `chat/index.html`。

## 许可

本项目以 Apache License 2.0 授权,全文见 [LICENSE](./LICENSE)。
