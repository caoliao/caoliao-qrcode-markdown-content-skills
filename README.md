**English** | [中文](./README.zh-cn.md)

# Caoliao QR Code Markdown Content Skill

Retrieve Markdown-formatted content from Caoliao QR code links.

## Overview

When a user provides a Caoliao QR code short link (e.g. `https://qr61.cn/oZwrwZ/q2wR1WE`), this skill automatically recognizes the link and returns the corresponding page content in Markdown format.

## Supported URL Formats

```
https://qr61.cn/{segment1}/{segment2}
https://qr71.cn/{segment1}/{segment2}
https://qr69.cn/{segment1}/{segment2}
https://h.qr61.cn/{segment1}/{segment2}
```

URLs may include query parameters.

## Installation

### Via npx skills (Recommended)

```sh
npx skills add caoliao/caoliao-qrcode-markdown-content-skills
```

Install for a specific agent:

```sh
npx skills add caoliao/caoliao-qrcode-markdown-content-skills -a cursor
npx skills add caoliao/caoliao-qrcode-markdown-content-skills -a claude-code
```

Install globally (available across all projects):

```sh
npx skills add caoliao/caoliao-qrcode-markdown-content-skills -g
```

### Via git clone

Navigate to your skills directory:

```sh
git clone https://github.com/caoliao/caoliao-qrcode-markdown-content-skills.git
```
