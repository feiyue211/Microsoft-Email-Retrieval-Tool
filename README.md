# Microsoft-Email-Retrieval-Tool
一个 Windows 桌面版微软邮箱 IMAP 收件器，用于快速连接 Outlook / Hotmail / Microsoft 邮箱，查看收件箱与垃圾箱邮件，并自动提取常见验证码。

## 功能特点

- 支持 Microsoft 邮箱 IMAP 连接。
- 支持密码登录，也支持 `Client ID + Refresh Token` 的 OAuth2 登录。
- 支持收件箱、垃圾箱和自定义文件夹读取。
- 支持按关键词、最近天数、邮件数量筛选。
- 邮件列表只读取邮件头，刷新速度更快。
- 支持读取完整正文、复制正文。
- 自动识别常见验证码、一次性代码、安全代码，并支持一键复制。
- 支持自动刷新，适合等待验证码邮件时使用。
- 无需浏览器登录，下载后可直接运行 exe。

## 使用方法

从 Release 下载：

```text
微软邮箱获取工具.exe
```

双击运行后，填写邮箱账号信息，点击 `连接`，连接成功后会自动刷新邮件列表。

## 账号填写格式

界面支持两种填写方式。

### 分栏填写

分别填写：

```text
邮箱
密码
Client ID
Refresh Token
```

密码登录时只需要填写邮箱和密码。

OAuth2 登录时填写邮箱、Client ID、Refresh Token。若没有密码，可以留空密码栏。

### 快速导入

支持以下格式：

```text
邮箱----密码----client_id----refresh_token
邮箱|密码|client_id|refresh_token
邮箱<TAB>密码<TAB>client_id<TAB>refresh_token
```

示例：

```text
example@hotmail.com----your_password----your_client_id----your_refresh_token
```

## 常见问题

### 连接失败

请检查：

- 邮箱和密码是否正确。
- Microsoft 账号是否开启 IMAP。
- 当前网络是否能访问 `outlook.office365.com:993`。
- 如果账号开启两步验证，普通密码可能无法登录，需要使用授权方式或可用的 OAuth2 信息。

### 收不到验证码

可以尝试：

- 勾选 `垃圾箱`。
- 增大 `数量`。
- 将 `近几天` 设置为更大的值，或设置为 `0` 搜索全部。
- 使用关键词筛选，例如平台名称、`code`、`验证码`。
- 开启自动刷新。

### 验证码没有自动识别

工具会匹配常见的 4-10 位数字、字母数字组合以及常见英文/中文验证码提示词。若邮件格式特殊，可以先读取正文，再手动复制正文中的验证码。

## 安全说明

- 本工具用于读取你本人拥有或已获授权的邮箱账号。
- 请勿将密码、Refresh Token、Client ID 提交到 GitHub。
- 建议不要在截图、Issue、日志中暴露账号凭据。
- 当前工具不需要额外后端服务，邮箱连接直接通过 Microsoft IMAP / OAuth2 接口完成。

## 文件说明

```text
微软邮箱获取工具.exe         Windows 可执行程序
README.md                  项目说明
```

## 许可

仅供个人学习、测试和授权场景使用。请遵守 Microsoft 服务条款以及当地法律法规。

## 许可

仅供个人学习、测试和授权场景使用。请遵守 Microsoft 服务条款以及当地法律法规。
