# 发布到 GitHub Pages

> 已完成（2026-11-10）：仓库 https://github.com/alitaforver801-debug/portfolio ，Pages https://alitaforver801-debug.github.io/portfolio/ 。
> 下面是以后换机/重建时的步骤。

> 前提：GitHub 账号 alitaforver801-debug 已登录（本机 `gh` token 已过期，需要重新登录：`gh auth login`）。

## 方式一：命令行（推荐）

```bash
cd 作品集站点
git init -b main
git add .
git commit -m "init: 个人作品集主页"
gh auth login                      # 若 token 失效，先重新登录
gh repo create portfolio --public --source=. --push
gh browse --web
```

然后打开仓库 **Settings → Pages**：
- Source 选 **Deploy from a branch**
- Branch 选 **main**，目录选 **/ (root)**
- 保存，等 1-2 分钟

访问地址：`https://alitaforver801-debug.github.io/portfolio/`

## 方式二：网页上传

1. 打开 https://github.com/new ，仓库名填 `portfolio`，选 Public，创建；
2. 页面点 **uploading an existing file**，把 `index.html`、`assets/`、`README.md` 拖进去，提交；
3. Settings → Pages → main / root → 保存。

## 自定义域名（可选）

如果有自己的域名，在 Pages 设置里填 Custom domain，并在域名服务商加 CNAME 记录指向 `alitaforver801-debug.github.io`。

## 之后怎么更新

改完 `index.html` 后：

```bash
git add . && git commit -m "update: 作品集" && git push
```

Pages 会在 1 分钟内自动更新。

## 注意

- 仓库是 **Public**，页面内容所有人可见；不要放私人联系方式以外的隐私信息（身份证、成绩单、聊天记录）。
- 简历 PDF 里的手机号/邮箱本来就用于投递，公开无碍；如果不想公开手机号，可只保留邮箱，或在 PDF 里换成"邮箱联系"。
- 作品集网盘链接、提取码如需更换，改 `index.html` 里两处 `pan.baidu.com/...`（搜索 `1XobOB6g`）和 README 一处。
