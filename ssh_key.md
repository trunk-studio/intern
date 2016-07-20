Github 目前提供兩種方式來進行遠端 repo 的操作，使用 HTTPS 或SSH。

如果使用 HTTPS 來進行操作的話，每次push程式碼都還必須要輸入帳號密碼，若使用 SSH，則只要設定過一次 Public Key之後，進行任何操作就不需要輸入帳號密碼， 讓 Git 的操作更加方便。

以下將說明生成 SSH Key 的步驟：

### 檢查是否有相關 SSH Key 存在

假如不確定以前是否有做過 SSH Key 的話，可以先檢查電腦是否有檔案。

1. 開啟 **命令提示字元** 或是 **Git Bash**
2. 在程式中輸入 `ls -al ~/.ssh` 來檢查是否有相關檔案

```
$ ls -al ~/.ssh
```
一般預設的公共密鑰文件為下列其中之一

- id_dsa.pub
- id_ecdsa.pub
- id_ed25519.pub
- id_rsa.pub

### 製作 SSH Key & 加入 SSH-Agent

###### 製作 SSH Key

1. 開啟 **命令提示字元** 或是 **Git Bash**

2. 輸入或是貼上下列指令， 並在 `""`中輸入自己的 GitHub email

```
$ ssh-keygen -t rsa -b 4096 -C "GitHub email address"
```
3. 輸入完按 `ENTER` 後會出現下列訊息：

```
Enter a file in which to save the key (/Users/you/.ssh/id_rsa)
```
可直接 `ENTER` 下一步

4. 設定 SSH Key 密碼

```
Enter passphrase (empty for no passphrase): 輸入密碼
```
```
Enter same passphrase again: 再輸入一次密碼
```

##### 加入 SSH-Agent

1. 確認 ssh-agent 啟動

```
$ eval "$(ssh-agent -s)"
```

##### 將 SSH Key 加入 GitHub 帳號中

1. 輸入以下指令，複製 SSH Key 至剪貼簿

```
$ clip < ~/.ssh/id_rsa.pub
```

2. 至 GitHub 頁面中，點選右上頭像旁的倒三角形，點選 `Settings`

![](/blog/content/images/2016/06/-----2016-06-16-16-31-37.png)
![](/blog/content/images/2016/06/-----2016-06-16-16-32-02.png)

3. 在左側設定列表中點選 `SSH and GPG keys`

![](/blog/content/images/2016/06/-----2016-06-16-16-32-21.png)

4. 選擇 `New SSH key`

5. **Title** 自行設定自己想要的名稱，把前面複製的 SSH Key 貼到中間框框裡，最後選擇 `Add SSH Key`

6. 選擇 `Add SSH Key` 後，需要輸入 GitHub 密碼做確認，確認成功後就完成把 Key 放進 GitHub 中了！

### 測試 SSH Key 聯繫

1. 開啟 **命令提示字元** 或是 **Git Bash**
* 輸入以下指令

```
$ ssh -T git@github.com
```
會出現以下相關訊息

```
The authenticity of host 'github.com (192.30.252.1)' can't be established.
RSA key fingerprint is 16:27:ac:a5:76:28:2d:36:63:1b:56:4d:eb:df:a6:48.
Are you sure you want to continue connecting (yes/no)?
```
```
The authenticity of host 'github.com (192.30.252.1)' can't be established.
RSA key fingerprint is nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
Are you sure you want to continue connecting (yes/no)?
```
輸入 `yes` ，出現以下訊息代表連結成功！
```
Hi username! You've successfully authenticated, but GitHub does not
provide shell access.
```

參考資料：

[Generating an SSH key](https://help.github.com/articles/generating-an-ssh-key/)
