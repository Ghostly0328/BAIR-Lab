
# 個人操作手冊

這份手冊提供了必要工具和快速登入伺服器的方法。

## 必備工具

- Visual Studio Code (VSCode)
- SSH (Secure Shell)

## 快速登入伺服器

要生成SSH金鑰對，包括公鑰和私鑰，請運行以下命令。持續按 Enter 以接受預設設定。

```bash
ssh-keygen
```

你可以使用以下其中一種方法將你的SSH公鑰添加到伺服器：

### 方法一：使用 ssh-copy-id

將 `username`、`server_host` 和 `your_key_path` 替換為你的用戶名、伺服器的IP地址或主機名，以及你的SSH金鑰的路徑。

```bash
ssh-copy-id -i your_key_path username@server_host
```

### 方法二：手動將公鑰添加到伺服器

首先，顯示你的公鑰：

對於Ubuntu：
```bash
cat ~/.ssh/ubuntu_id_rsa.pub
```

對於Windows：
```bash
code C:\Users\*YOURUSERNAME*\.ssh\id_rsa.pub
```

你將看到你的公鑰，看起來像這樣：

```bash
ssh-rsa xxxxx xxxx@xxxx.com
```

複製你的公鑰。然後，登入伺服器並將此公鑰添加到你的用戶帳戶的 `~/.ssh/authorized_keys` 文件。如果文件不存在，創建它。如果它存在，將公鑰添加到文件末尾的新行。
