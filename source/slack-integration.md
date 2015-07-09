[(via)](http://logme.logdown.com/posts/284361/slack-tips-1-how-to-add-trello-as-an-integration)
本文將介紹Slack如何新增Integration。
<img class="center" src="http://user-image.logdown.io/user/4926/blog/4929/post/284361/HDjaYiEQkicc4dmuGZOM_slackinteration.PNG" alt="slackinteration.PNG">
<!--more-->

## 幹嘛要加入Integration？
具體來說可以幹嘛？
> 替你轉某個Twitter用戶的推文到特定頻道中、通知你某個Trello的Board有內容更動，或是透過Slack提供的輸出入API，將APP的錯誤訊息傾印到某個頻道裡（或反過來蒐集特定字詞的聊天記錄到Google Doc中）；甚至是，如果有人Push任何內容到你的Github，Slack都會忠實的提醒你。

## 什麼是Integration？
老實說我先前一直把它看成是Ingredient。你可以把它當成你的全自動血汗助理：
> 提供類似像是[IFTTT](https://www.google.com.tw/url?sa=t&rct=j&q=&esrc=s&source=web&cd=3&cad=rja&uact=8&ved=0CDMQFjACahUKEwiKjc6RmczGAhWMBo4KHcaGAsY&url=http%3A%2F%2Fwww.techbang.com%2Fposts%2F10353-network-service-automation-application-ifttt-get-fb-maps-pchome-199-skills&ei=QnCdVYrkIYyNuATGjYqwDA&usg=AFQjCNF53JuALe8_roIQckoxaJS93funuA&sig2=J0BGrwNTJl8n5xOX1K1Icw)一樣的功能，連結各種網路服務之後，自動推播到指定的channel上，你再也不用追著各種服務的狀態跑了。Be less busy.

## 支援哪些服務？
來看看目前[已支援的服務清單](https://slack.com/integrations)；以及[即將支援的服務清單](https://slack.zendesk.com/hc/en-us/articles/202035138-Upcoming-Slack-integrations)。

## 有什麼限制嗎？
不管說的多麼天花亂墜，只要這服務需要收費，那就都是多餘的了；反過來說，再怎麼少也聊勝於無。

Slack有給一個Team總共免費五個的額度（注意:是整個Team共用5個)：
<img class="center" src="http://user-image.logdown.io/user/4926/blog/4929/post/284361/0AttKUrqQR6o7ZMxD09w_limit.PNG" alt="limit.PNG">

## 怎麼開始？
廢話不多說，立刻開始操作！無論是網頁版或是Win/Mac應用程式，你都可以在兩個地方找到加入Integration的按鈕，分別是：Channel/Private Group的標題選單中，或空白的對話視窗裡：
<img class="center" src="http://user-image.logdown.io/user/4926/blog/4929/post/284361/FAUD3nqT6vNVmTFs3NAm_%E5%9C%96%E7%89%871.png" alt="addaintergration">

點下之後會跳到一個新的網頁：
<img class="center" src="http://user-image.logdown.io/user/4926/blog/4929/post/284361/WjvRT7N8ScSOY253Wc8n_slackinterationlist.PNG" alt="slackinterationlist.PNG">

每個Integration都有各自不同的細部設定，這邊我以[Trello](https://trello.com/)為例。

首先，我們需要給予授權，同時選定一個當Trello有任何異動時，需要被通知的Channel/PrivateGroup/**People**：
<img class="center" src="http://user-image.logdown.io/user/4926/blog/4929/post/284361/Jsb5BgAtQ8iejsy51XOr_slackinterationtrello.PNG" alt="slackinterationtrello.PNG">

授權後可以選定哪一個Board異動時才連動到Slack，同時還能選擇是哪些事件才觸發：
<img class="center" src="http://user-image.logdown.io/user/4926/blog/4929/post/284361/klgxJjzTRmRr48mtWTMQ_trelloslacksetting.PNG" alt="trelloslacksetting.PNG">

當然還有一些更詳細的設定，例如Post出現時的Icon、Tag等等之類的。都選完之後，只要Trello出現符合設定的事件，你的Slack就會出現像這樣的通知：
<img class="center" src="http://user-image.logdown.io/user/4926/blog/4929/post/284361/M37Ob2k9Ru60zBXVDKBl_trelloreaction.PNG" alt="trelloreaction.PNG">

##結語
怎麼樣？很不賴吧！希望你會喜歡。以下雜列了Slack自己給的幾個教學，有興趣不妨一試：
- [Setting up the GitHub integration](https://slack.zendesk.com/hc/en-us/articles/201824286-Setting-up-the-GitHub-integration)
- [Sharing Box files in Slack](https://slack.zendesk.com/hc/en-us/articles/205023018-Sharing-Box-files-in-Slack)
- [Sharing Google Drive files in Slack](https://slack.zendesk.com/hc/en-us/articles/205875058-Sharing-Google-Drive-files-in-Slack)
