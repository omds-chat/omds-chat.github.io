# omdsc-dev.github.io

omdsc-dev 组织的在线 Pages 站点仓库。站点内容全部是静态文件,由 GitHub Pages 直接托管本仓库根目录,不经过任何构建流程。

## 目录结构

| 路径 | 说明 |
|:---:|:---:|
| `index.html` | 组织站点首页,列出组织对外提供的各个入口。 |
| `chat/index.html` | 在线聊天入口,访问后跳转到 DeepSeek-Chat-Enhanced 的 Pages 页面。 |
| `.nojekyll` | 空文件,关闭 GitHub Pages 的 Jekyll 处理,保证文件按原样发布。 |
| `README.md` | 本说明文件。 |
| `.gitignore` | 忽略规则,排除依赖目录、日志与临时目录。 |
| `LICENSE` | Apache License 2.0 全文。 |

## chat/ 的跳转用途

`chat/index.html` 是一个纯静态跳转页,跳转目标固定为:

```text
https://omdsc-dev.github.io/DeepSeek-Chat-Enhanced/
```

跳转由两条路径完成:

- `<meta http-equiv="refresh" content="0; url=...">` 作为无脚本环境下的兜底。
- 一段极简内联脚本执行 `location.replace()`,在脚本可用时优先跳转,且不向浏览器历史记录写入多余条目。

页面正文保留一行提示与一个可点击的备用链接,目标页面不可达时用户仍可手动进入。该页面不做任何可达性探测,也不引入任何外部资源,样式与脚本全部内联。

## 本地预览

任意静态服务器均可。在仓库根目录任选一条命令:

```bash
npx serve .
```

```bash
python -m http.server 8000
```

首页访问 `http://localhost:8000/`,跳转页访问 `http://localhost:8000/chat/`。

## 部署

GitHub Pages 直接托管本仓库根目录:在仓库的 Pages 设置中把发布源指向默认分支的根目录(`/`),无需构建步骤与额外产物,Pages 直接分发仓库内的静态文件。`.nojekyll` 的存在确保 `chat/` 等目录与文件不经过 Jekyll 处理。

## 许可

本项目以 Apache License 2.0 授权,全文见 [LICENSE](./LICENSE)。
