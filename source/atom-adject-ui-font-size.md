([from](http://logme.logdown.com/posts/285175/atom-tips1how-to-adjust-ui-font-size-font-size-how-to-adjust-the-interface))
<img class="center" src="https://upload.wikimedia.org/wikipedia/commons/2/24/Atom-text-editor.png">

本文將介紹如何修改特定幾處 ATOM 介面元件的字體大小：
- Tree-View
- Tab-Title
- Setting-View

<!--more-->
    
Atom是近期非常火紅的一款多文字編輯器/前端設計工具，Atom是由GitHub開發的自由及開放原始碼的文字與程式碼編輯器，支援OS X、Windows和Linux作業系統，支援Node.js所寫的外掛程式，並內建Git版本控制系統（via [Wiki](https://zh.wikipedia.org/wiki/Atom_(%E6%96%87%E5%AD%97%E7%B7%A8%E8%BC%AF%E5%99%A8))）。簡列幾個好處：
- 介面潮
- 樹狀目錄view非常方便
- 有比sublime方便的套件安裝介面

##OK，那我改字體大小幹嘛？
Atom 的字體大小設定影響的是編輯器內文的大小，不影響介面字體的大小。我自己用的筆電配備 2K 螢幕，在 windows 下沒有問題，但在 Ubuntu 下問題就大了。看看左邊的 tree-view 和 tab 上的字，這樣是怎麼讀！
<img class="center" src="http://user-image.logdown.io/user/4926/blog/4929/post/285175/EBt3GVCR96EnYgILAlfo_atom1.PNG" alt="atom1.PNG">
真的太小了，即便改過 Ubuntu 的 Scale 大小，一樣都太小。

##怎麼做？
這邊將介紹怎麼修改介面字體大小。你會發現──這完全就是在改 CSS 嘛。在主選單中找到**[View]**-->**[Preference]**，或快速鍵**[Ctrl] + [,]**。
<img class="center" src="http://user-image.logdown.io/user/4926/blog/4929/post/285175/zEBSUmjQJ6Vbr5n4KUbg_atom2.jpg" alt="atom2.jpg">
然後找到左側 tree-view 中的 style.less 檔案。
<img class="center" src="http://user-image.logdown.io/user/4926/blog/4929/post/285175/mk37gTniQ3i7YhKpvib8_atom3.jpg" alt="atom3.jpg">
好，然後隨便找個空白處照以下輸入：
<img class="center" src="http://user-image.logdown.io/user/4926/blog/4929/post/285175/7kcB96bjSLSAfJbfgpm3_atom4.PNG" alt="atom4.PNG">
這樣就完成了，很簡單吧！如果你想改其他地方，可以試著猜該介面的可能命名，然後照 CSS 方式修改就可以了。
<img class="center" src="http://user-image.logdown.io/user/4926/blog/4929/post/285175/Mjg8BTUSJSDXc66kIF5j_atom5.PNG" alt="atom5.PNG">

##結語
先來看看對比圖，這種尺寸才正常啊！
<img class="center" src="http://user-image.logdown.io/user/4926/blog/4929/post/285175/PnDcVh0SoiqMa7YfoZCX_atom6.PNG" alt="atom6.PNG">

以下列出幾個我找資料時用到的網址，如果你有興趣不妨一逛，也許有一些我的漏網之魚，也請不吝指教。

- [How to set the font for the settings UI and the command browser](https://discuss.atom.io/t/how-to-set-the-font-for-the-settings-ui-and-the-command-browser/13498)
- [Font size too small in the settings GUI. #4342](https://github.com/atom/atom/issues/4342)
- [Anyway to change UI/tab/tree view font size? #2530](https://github.com/atom/atom/issues/2530)
- [Is it possible to increase the font size in tab headers?](https://discuss.atom.io/t/is-it-possible-to-increase-the-font-size-in-tab-headers/9386)


