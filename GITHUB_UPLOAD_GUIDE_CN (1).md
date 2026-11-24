# GitHub 上传操作说明（本包尚未公开发布）

1. 将本 ZIP 解压到本地，例如 `E:\mcpp-coupled-path-search`。
2. 检查 `README.md`、`LICENSE`、`LICENSE-CC-BY-4.0.md`、`LICENSE_SCOPE.md`、`OSM_DATA_LICENSE.md` 和 `PROVENANCE_RECONCILIATION.md`。代码采用 MIT；作者原创非代码研究材料采用 CC BY 4.0；OSM 派生数据库及嵌入的 OSM 数据内容采用 ODbL 1.0。核对版权主体、OSM 标注及混合文件的许可边界。
3. 在 GitHub 新建空仓库 `mcpp-coupled-path-search`。本包尚未公开发布；在选择 Public 前，完成 `PREFLIGHT_BEFORE_PUBLICATION.md` 的所有核查。不要勾选自动生成 README、LICENSE 或 .gitignore（本包已包含这些文件）。
4. 在解压目录打开终端执行：

```bash
git init
git branch -M main
git add .
git status
git commit -m "Initial research release for MCPP coupled-path search"
git remote add origin https://github.com/<YOUR_GITHUB_USERNAME>/mcpp-coupled-path-search.git
git push -u origin main
```

5. 推送后逐项检查 GitHub 上的文件数量、`README.md` 显示、`pair_audit.csv` 下载、源代码、OSM 许可和运行证据。
6. 再创建 GitHub Release（例如 `v1.0.0`），然后连接 Zenodo 归档该 Release 并取得 DOI。取得 DOI 后再更新论文 Data Availability Statement。

本包不包含 GitHub 凭据，也不会自动创建或公开仓库。单个文件上传前仍需检查 GitHub 当前文件大小限制；本包内所有单文件应低于 100 MiB。
