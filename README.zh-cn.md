[English](./README.md) | **中文**

# 草料二维码 Markdown 内容获取 Skill

用于从草料二维码链接中获取页面的 Markdown 格式内容。

## 功能说明

当用户提供草料二维码的短链接（如 `https://qr61.cn/oZwrwZ/q2wR1WE`）时，本 Skill 会自动识别并获取该链接对应的 Markdown 内容返回给用户。

## 支持的 URL 格式

```
https://qr61.cn/{segment1}/{segment2}
https://qr71.cn/{segment1}/{segment2}
https://qr69.cn/{segment1}/{segment2}
https://h.qr61.cn/{segment1}/{segment2}
```

URL 末尾可以带 query 参数。

## 安装

### 通过 npx skills 安装（推荐）

```sh
npx skills add caoliao/caoliao-qrcode-markdown-content-skills
```

安装到指定 agent：

```sh
npx skills add caoliao/caoliao-qrcode-markdown-content-skills -a cursor
npx skills add caoliao/caoliao-qrcode-markdown-content-skills -a claude-code
```

全局安装（跨项目可用）：

```sh
npx skills add caoliao/caoliao-qrcode-markdown-content-skills -g
```

### 通过 git clone 安装

进入 skills 目录：

```sh
git clone https://github.com/caoliao/caoliao-qrcode-markdown-content-skills.git
```
