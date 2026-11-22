# 受害者信息页（victims/index.html）

面向欧美 + 中文受害者的公开信息页，用途只有一个：让受害者知道去哪报案，并（可选）把公开陈述交给案件材料。

## 发布前必须改的两处

1. ~~`CONTACT_EMAIL_PLACEHOLDER`~~ 已填入 `taichang-case@outlook.com`（2026-11-22 注册）。换邮箱时全文件搜索替换即可。
2. `Last updated: 2026-11-22` —— 每次改动更新日期。

## 三条纪律

- **页面里不出现任何钱包地址**。受害者靠品牌名和 App 名认出自己，地址比对在我们的台账里做，不公开。
- 已加 `<meta name="robots" content="noindex,nofollow">`，不被搜索引擎收录，只通过公开帖子下的留言引流。
- 不承诺退款、不收费、不冒充任何机构；不收集身份证件。

## 部署（三选一）

### A. GitHub Pages（免费，需先把文件传上去）
1. 打开 https://github.com/new ，仓库名 `taichang-victims`，选 Public，创建
2. 点 "uploading an existing file"，把 `index.html` 拖进去，Commit
3. Settings → Pages → Source 选 `Deploy from a branch`，Branch 选 `main` / `root`，Save
4. 等 1 分钟，地址是 `https://xiaofeigetf.github.io/taichang-victims/`

> 本机 git 数据通道不稳，别用 `git push`；网页上传最稳。要自动化得装 `gh` 并用 API 上传。

### B. Netlify Drop（最快，不需账号也能先预览）
1. 打开 https://app.netlify.com/drop
2. 把整个 `victims` 文件夹拖进去
3. 拿到临时域名；要长期用需登录绑定

### C. Cloudflare Pages
登录后 Create project → Direct upload → 拖文件夹。国内访问比 GitHub Pages 稳。

## 引流方式（合规）

只在**公开帖子**下面留言贴链接：Forex Peace Army、Trustpilot、Reddit r/Scams、Facebook 受害者群、YouTube 打假视频评论区。
不要私信陌生人，不要群发邮件，不要买名单。

## 配套：证据来源台账

```bash
python3 scripts/provenance.py add <文件> --source "<URL 或 internal>" --note "说明"
python3 scripts/provenance.py list
python3 scripts/provenance.py verify     # 重新算哈希，确认没被改动
python3 scripts/provenance.py table      # 生成 Markdown 表，贴进给 FBI 的材料
```

台账在 `data/provenance.csv`，每行 = 文件 + 来源 + 获取时间(UTC) + SHA-256。
FBI 问"证据怎么来的"，给这张表，不要口头解释。
