# CNKI RefWorks 批量分析工具

上传 CNKI RefWorks 导出的 `.txt` 文件，按年份统计发文量、按刊源统计文章数。支持多文件合并统计和 CSV 导出。

## 功能

- 支持多选 / 拖拽上传多个 `.txt` 文件
- 自动解析 `YR` / `PY` / `DA` 字段提取发刊年份
- 自动解析 `JF` / `JO` / `T2` / `JA` 字段提取刊源
- 每个年份显示发文量和占比，每个刊源显示文章数和占比
- 汇总卡片：文件数 / 总文章数 / 年份种类 / 期刊种类
- 支持排序切换、CSV 导出（带 BOM，Excel 可直接打开）
- 可单独移除某个文件并实时重算
- 纯前端实现，文件不上传服务器，全部在浏览器内处理

## 本地使用

直接用浏览器打开 `index.html` 即可，无需安装依赖、无需构建。

## 部署到 Render

1. 上传本仓库到 GitHub
2. 登录 [render.com](https://render.com)，用 GitHub 账号登录
3. 点击 **New +** → **Static Site** → 选择本仓库
4. 填写配置：
   - **Branch**: `main`
   - **Build Command**: 留空
   - **Publish Directory**: `.`
5. 点击 **Create Static Site**，约 30 秒后上线

如果仓库里包含 `render.yaml`，也可以改用 **New +** → **Blueprint** 自动读取配置。

## 自定义解析字段

如果 CNKI 导出的字段名不同，修改 `index.html` 中 `parseRefWorks` 函数里的判断条件即可。例如把 `tag === 'YR'` 改成你实际使用的年份字段名。

## License

MIT