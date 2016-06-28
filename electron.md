# electron

## 參考文件

- blog: <https://blog.othree.net/log/2015/08/03/electron-intro/>
- slide: <https://speakerdeck.com/dannvix/electron-x-react-qian-duan-kai-fa-zhe-gao-su-kua-jie-zhuo-mian-kai-fa>
- gitbook: <https://www.gitbook.com/book/imfly/electron-docs-gitbook/details/zh-TW>

## IPC 介紹

<https://imfly.gitbooks.io/electron-docs-gitbook/content/zh-TW/api/ipc-main-process.html>

### IPC 使用注意

<https://github.com/seanchas116/electron-safe-ipc>

> DEPRECATED: Use Electron ipc within preload script instead Because of several problems (such as this issue or this limitation), I decided to deprecate electron-safe-ipc. Instead, I recommend using Electron ipc API within preload scripts.

使用官方 IPC 即可，雖然 promise 很好用

## Building Windows apps from non-Windows platforms

透過 Homebrew 安裝 wine

<https://github.com/electron-userland/electron-packager#building-windows-apps-from-non-windows-platforms>

## 參考專案

- System Check Demo: <https://github.com/trunk-studio/electron-demo>
- electron react redux sample: <https://github.com/chentsulin/electron-react-boilerplate>
- kitematic: <https://github.com/docker/kitematic>
