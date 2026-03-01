---
name: caoliao-qrcode-markdown-content
description: 从草料二维码链接获取 Markdown 内容。当用户提供匹配 qr61.cn、qr71.cn、qr69.cn 或 h.qr61.cn 域名且路径为两段的 URL 时，或要求获取草料二维码链接内容时使用。
---

# 草料二维码 Markdown 内容获取

在草料二维码短链接末尾拼接 `.md` 后缀，获取页面的 Markdown 格式内容。

## URL 格式

匹配规则：`https://{domain}/{segment1}/{segment2}[?query]`

- 支持的域名：`qr61.cn`、`qr71.cn`、`qr69.cn`、`h.qr61.cn`
- 路径：恰好两段（如 `oZwrwZ/q2wR1WE`），每段为字母数字字符
- URL 末尾可以带 query 参数，不影响校验

示例：
- `https://qr61.cn/oZwrwZ/q2wR1WE`
- `https://qr71.cn/oZwrwZ/q2wR1WE`
- `https://h.qr61.cn/oZwrwZ/q2wR1WE?a=1`

## 工作流程

1. **校验 URL** — 确认域名为 `qr61.cn`/`qr71.cn`/`qr69.cn`/`h.qr61.cn` 之一，路径恰好为两段且非空。
2. **构造请求 URL** — 在路径末尾追加 `.md`（query 参数保留在 `.md` 之后）：
   ```
   https://qr61.cn/oZwrwZ/q2wR1WE       →  https://qr61.cn/oZwrwZ/q2wR1WE.md
   https://h.qr61.cn/oZwrwZ/q2wR1WE?a=1  →  https://h.qr61.cn/oZwrwZ/q2wR1WE.md?a=1
   ```
3. **通过 Shell 工具使用 `curl` 获取内容**，根据操作系统选择对应命令：

   **Windows (PowerShell):**
   ```powershell
   curl.exe -L -s "https://qr61.cn/oZwrwZ/q2wR1WE.md"
   ```

   **macOS / Linux:**
   ```bash
   curl -L -s "https://qr61.cn/oZwrwZ/q2wR1WE.md"
   ```

   > Windows 下必须使用 `curl.exe` 而非 `curl`，避免 PowerShell 将其解析为 `Invoke-WebRequest`。

4. **将获取到的 Markdown 内容返回给用户**。若请求失败或返回错误，告知用户具体问题。

## 注意事项

- `-L` 参数用于跟随重定向。
- `-s` 参数用于静默输出，不显示进度信息。
- 如果路径末尾有斜杠 `/`，需先移除再拼接 `.md`。
- 如果 URL 带有 query 参数（`?key=value`），`.md` 应插入在 path 和 `?` 之间。
