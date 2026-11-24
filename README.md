# 泰昌案 · 受害者信息页

**在线地址：https://taichang-case.github.io/taichang-victims/**

面向本案受害者的公开信息页。用途只有一个：让被骗的人知道去哪报案，并（可选）把公开陈述交给案件材料。

- 页面源文件：`index.html`（本目录）
- 部署：`bash ../scripts/deploy_victims.sh`（同时推 `main` 与 `gh-pages`，Pages 从 gh-pages 构建）
- 当前状态：`<meta name="robots" content="index,follow">`，已提交 sitemap 与 IndexNow；页面里**不出现任何钱包地址**

## 页面纪律

- 不出现钱包地址。受害者靠品牌名和 App 名认出自己，地址比对在台账里做。
- 不承诺退款、不收费、不冒充任何机构；不收集身份证件。
- 只引导报案：IC3 / `TaiChangTIPS@fbi.gov` / 当地警方。

## 改完之后

1. 更新 `index.html` 里的 `Last updated:` 日期
2. `bash ../scripts/deploy_victims.sh`（git 推送已实测可用，两个分支都要推）
3. 抓一次线上页面，确认 md5 与本地一致（Pages 重建约 1 分钟）

## 引流

只在**公开帖子**下留言：Reddit r/Scams、Forex Peace Army、Chainabuse、Facebook 受害者群、YouTube 打假视频评论区。
不私信陌生人、不群发、不买名单。渠道细节见 `../docs/seeding-channels.md`。

## 证据来源台账

```bash
python3 scripts/provenance.py add <文件> --source "<URL 或 internal>" --note "说明"
python3 scripts/provenance.py verify     # 重算哈希
python3 scripts/provenance.py table      # 生成 Markdown 表，直接贴进材料
```
