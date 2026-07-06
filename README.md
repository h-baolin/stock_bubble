# 股票气泡图看板 GitHub Pages 发布包

这个目录是从本地项目生成的静态发布副本，只用于上传到 GitHub Pages。
它不包含飞书 webhook、`.env`、本地脚本源码和桌面面板文件。

## 目录内容

- `index.html`：飞书和浏览器打开的气泡图入口。
- `sector_dashboard_data.json`：气泡图数据快照。
- `kline_charts/`：每个气泡点击后打开的日线 K 线页面。
- `stock_watch.xlsx`：Excel 统计表副本，方便留档或下载查看。
- `.nojekyll`：让 GitHub Pages 原样发布静态文件。
- `FEISHU_CARD_TEMPLATE.json`：飞书自定义机器人消息卡片模板。

## 发布到 GitHub Pages

1. 在 GitHub 创建一个新仓库，例如 `stock-bubble-dashboard`。
2. 只上传本目录 `github_pages_dashboard` 里面的文件，不要上传整个 `股票量化` 工作区。
3. 在仓库 Settings -> Pages 中选择从 `main` 分支的根目录发布。
4. 发布成功后，访问地址通常是：

```text
https://你的用户名.github.io/stock-bubble-dashboard/
```

这个地址就是后续放进飞书卡片按钮里的看板链接。

## 每天盘后更新

先在本地刷新原始看板，再重新生成这个发布包，最后在本目录对应的 GitHub 仓库中提交并推送：

```powershell
git add .
git commit -m "Update stock dashboard"
git push
```

如果只是先手动验证，也可以直接把本目录文件拖到 GitHub 网页端上传。

## 安全边界

- 本目录是公开网页内容；如果 GitHub 仓库公开，股票池、Excel 副本和 K 线页面也会公开。
- 不要把 `.env.local`、飞书 webhook、桌面面板脚本、整个项目目录上传到公开仓库。
- 飞书消息只需要放 GitHub Pages 链接，不需要把 webhook 写进网页。
