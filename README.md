長庚大學 大數據分析方法 作業三
================

網站資料爬取
------------

``` r
library(rvest)
```

    ## Warning: package 'rvest' was built under R version 3.3.3

    ## Loading required package: xml2

    ## Warning: package 'xml2' was built under R version 3.3.3

``` r
job_list<-list()

for(i in 2571:2579){
Tech_Job<-paste("https://www.ptt.cc/bbs/Tech_Job/index",i,".html",sep="")
Title<-read_html(Tech_Job)%>%
html_nodes(".title")%>%
html_text()  
PushNum<-read_html(Tech_Job)%>%
html_nodes(".nrec")%>%
html_text()
Author<-read_html(Tech_Job)%>%
html_nodes(".author")%>%
html_text()
frame<-data.frame(Title=Title,PushNum=PushNum,Author=Author)
job_list[[i]]<-frame
}
dataframeall<-rbind(job_list[[2571]],job_list[[2572]],job_list[[2573]],job_list[[2574]],job_list[[2575]],job_list[[2576]],job_list[[2577]],job_list[[2578]],job_list[[2579]])
```

爬蟲結果呈現
------------

``` r
#這是R Code Chunk
knitr::kable(dataframeall)
```

| Title                                                            | PushNum | Author       |
|:-----------------------------------------------------------------|:--------|:-------------|
| \[請益\] 台橡化工技術員面試一職                                  |         | minwoo0904   |
| \[請益\] 台塑宜蘭廠                                              | 9       | nerlens      |
| \[請益\] acer system engineer                                    |         | ccc0901      |
| Re: \[心得\] 南u製程工作心得                                     | XX      | livefishfish |
| \[面試\] 台積設備/應材客服/南亞科設備 請益                       | 9       | s50190       |
| Re: \[情報\] 106年IC layout人才養成班 (代PO)                     | 9       | SUPER22K     |
| Re: \[請益\] 另一半認為, 7:00下班是不顧家庭                      | 21      | Feases       |
| \[心得\] 船舶暨海洋產業研發中心 面試心得                         | 14      | kevin505     |
| Re: \[請益\] 另一半認為, 7:00下班是不顧家庭                      | 50      | cjb          |
| \[請益\] 科技部工作經歷在Linkedin上的名稱                        | 1       | Paravion     |
| Re: \[新聞\] 海邊台大校園徵才圓滿落幕　收穫逾2000履歷表          | 31      | LibertyWings |
| Re: \[請益\] 另一半認為, 7:00下班是不顧家庭                      | 7       | zxlu         |
| \[討論\] 程式語言筆試面試的準備                                  | 1       | magic704226  |
| \[請益\] 大公司的話 個資可以放心填?                              |         | jason050117  |
| \[請益\] OFFER選擇 (群創光電V.S台電機械職員                      | 53      | Moran        |
| \[請益\] 請問螃蟹的Android/Media軟體設計工程師                   | 1       | magic704226  |
| Re: \[請益\] 另一半認為, 7:00下班是不顧家庭                      | 爆      | AK47shoot    |
| \[請益\] 大立光物管工程師                                        | 14      | omes4219     |
| Re: \[請益\] 另一半認為, 7:00下班是不顧家庭                      | 42      | TSMCer       |
| \[徵才\] EasyStack徵才年薪120萬台幣起                            | 10      | mimi0213     |
| \[請益\] 請教大碩面試後等通知需要等多久？                        | 19      | uasalada     |
| Re: \[請益\] OFFER選擇 (群創光電V.S.台電機械職                   | 18      | lsz6404      |
| \[請益\] 台積電 EMITD 工作內容                                   | 19      | innocentguy  |
| \[新聞\] ic設計每股獲利洗牌 聯發科跌落3名外                      | 20      | LBJ2ndKing   |
| \[請益\] 住華 新技術開發 and 奇美材 製程 詢問                    | 5       | Edwardkiller |
| \[請益\] 研替offer(京元/緯創）                                   | 7       | starjli      |
| \[請益\] 碩一暑期實習                                            | 5       | a29417557    |
| Re: \[請益\] 另一半認為, 7:00下班是不顧家庭                      | 5       | HateAnus     |
| \[請益\] 水果公司的工廠，工程師好跳嗎？                          | 17      | ggggggh      |
| \[面試\] 化工面試 住友/三井/花王/景碩/陶麗西/新光/清錄/麥特/艾克 | 57      | BCCAT        |
| Re: \[請益\] 另一半認為, 7:00下班是不顧家庭                      | 30      | unclefucka   |
| Re: \[請益\] 另一半認為, 7:00下班是不顧家庭                      | 1       | cacalota     |
| Re: \[請益\] 另一半認為, 7:00下班是不顧家庭                      | 17      | jessicabana  |
| Re: \[請益\] 另一半認為, 7:00下班是不顧家庭                      | 19      | soufon       |
| \[心得\] 小公司的慎選...                                         |         | JT0816       |
| \[閒聊\] 海邊的一盤大棋                                          | 28      | balzark      |
| Re: \[請益\] 另一半認為, 7:00下班是不顧家庭                      | 36      | smallchou    |
| \[請益\] 請問應徵台積OP是否有黑名單                              | 37      | kn0105209    |
| \[新聞\] 郭台銘：陸大學生動手能力差                              | 21      | BBMADE       |
| Re: \[新聞\] 郭台銘：陸大學生動手能力差                          |         | schizophrena |
| \[新聞\] 斥資600億 「綠能科學城」落腳台南沙崙                    | 26      | hottea88310  |
| 滷肉開獎                                                         | 57      | crafttt      |
| \[新聞\] 台積電3奈米廠出走？傳5000億落腳美國                     | 51      | popoallan    |
| Re: \[新聞\] 台積電3奈米廠出走？傳5000億落腳美國                 | 5       | appledavid   |
| \[新聞\] 台積電成環評箭靶　網友酸農地工廠卻就                    | 31      | wahaha23     |
| Fw: \[新聞\] 新世代最崇拜企業家　郭董取代賈柏斯                  | X4      | tw689        |
| \[請益\] 工作上想成長,想上點課程~                                | 7       | kevinZJL     |
| Re: \[心得\] 小公司的慎選...                                     | 1       | Sex5F        |
| \[請益\] 研替or一般替代役                                        | 34      | charisma007  |
| \[請益\] 達運光電(五股)                                          |         | smst         |
| \[情報\] 106年03月22日\_竹科\_IC設計產業座談會                   | 1       | SuperModel   |
| Re: \[請益\] 點序科技業務職面試請益                              | 2       | hueepf       |
| \[情報\] 整合深度學習的無人駕駛新創公司Drive.ai                  | 5       | zxcvxx       |
| \[請益\] 慧盛先進科技？                                          | 1       | amethystleaf |
| \[請益\] 3/11長春體檢                                            | 10      | elvisman     |
| \[新聞\] 績效獎金打6折？ 聯詠：不予回應                          | 13      | PerfectID    |
| \[新聞\] 台積電 3 奈米赴美？關鍵在量子電腦                       | 16      | evil7589     |
| \[請益\] 求職心力憔悴                                            | 66      | rko801024    |
| \[請益\] 代PO 交大半導體碩專班一問                               | 5       | remember246  |
| Re: \[請益\] 另一半認為, 7:00下班是不顧家庭                      | 13      | yolosiku     |
| \[面試\] 關於弘塑科技業務工程師                                  | 2       | onlyveritas  |
| \[請益\] 自行保公會勞健保                                        | 2       | ann3222      |
| \[面試\] 南科艾爾斯半導體                                        | 5       | turtle6188   |
| \[新聞\] 謝金河：台積電打敗Intel！已是全球第一                   | 11      | soaping      |
| Re: \[請益\] 水果公司的工廠，工程師好跳嗎？                      | 7       | nomilkman    |
| Re: \[新聞\] 台積電 3 奈米赴美？關鍵在量子電腦                   |         | pig2014      |
| \[聘書\] offer 機構 vs 半導體CSE                                 | 5       | bboycookie   |
| \[請益\] 沒有中生代的公司                                        | 9       | randomly     |
| \[請益\] 測試/系統整合/自動化工程師                              | 2       | foreverwhat  |
| Re: \[新聞\] 績效獎金打6折？ 聯詠：不予回應                      | 3       | jeromeshih   |
| Re: \[請益\] 水果公司的工廠，工程師好跳嗎？                      |         | typewindow   |
| Re: Fw: \[新聞\] 新世代最崇拜企業家　郭董取代賈柏斯              |         | jeromeshih   |
| \[心情\] 連來台灣的外國朋友都會講"台積電"華文                    | 8       | terimakasih  |
| \[請益\] 獵人頭 網站 or APP                                      | 16      | sustaned     |
| \[新聞\] 台積電赴美設廠？ 科技部轉述：並無此計                   | 19      | TrueSpace    |
| \[請益\] 螃蟹OFFER請益(代PO)                                     | 6       | birdhackor   |
| \[請益\] 以下加班申請定合理嗎?                                   | 9       | zaxck        |
| Re: \[請益\] 獵人頭 網站 or APP                                  | 8       | appledavid   |
| \[請益\] 半年的技術員經歷                                        | 16      | ak080775     |
| \[請益\] 宏騰光電一些問題...                                     | 3       | qqming0721   |
| Fw: \[徵才\] 興豪傳媒科技 誠徵Javascript前端工程師               | 1       | cliffk321    |
| \[請益\] 福爾摩莎紙業股份有限公司高雄業務                        |         | edison81630  |
| \[聘書\] 研替offer請益(皮卡)                                     | 5       | paulu90      |
| \[新聞\] 吞iPhone緯創資本支出破百億　3年新高                     | 11      | qazxc1156892 |
| \[新聞\] 陳良基：與張忠謀溝通過「所有投資以台灣為優先            | 13      | wer11        |
| \[請益\] 竹科聯電製程                                            | 9       | berac16      |
| \[新聞\] 讀軍校免當軍人 中科院上班54K                            | 18      | tw689        |
| \[請益\] 日月光-歐美區(美國)客戶關係管理                         | 11      | lim10337     |
| \[請益\] 南科住華科技                                            | 12      | kurtgod      |
| \[請益\] Nvidia的Android Framework/SW Engineer                   | 16      | magic704226  |
| \[請益\] 亞德客or鑫陽鋼鐵                                        | 6       | eraser90310  |
| \[請益\] 云辰科技                                                |         | Intelgence   |
| \[請益\] NXP Service Engineer                                    | 7       | angelpeace   |
| \[情報\] 千竣科技違反勞基法，官司結果                            | 50      | GameHeven    |
| \[新聞\] 台積電試產 7 奈米良率超過七成                           | 43      | unrest       |
| \[請益\] 台積電的設備自己研發?                                   | 55      | sustaned     |
| \[請益\] offer選擇                                               | 7       | queenghost   |
| \[討論\] 公司要資遣人，需要通報勞工局嗎？                        | 12      | JE2K         |
| \[新聞\] 新日光虧損破紀錄 去年財報淨損63.1億                     | 16      | moonth66     |
| \[新聞\] 竹科IC產業衰退？ 科管局：研發力道仍強                   | 8       | breath35     |
| \[請益\] 走品質的有可能年薪破百嗎?                               | 21      | DUFA         |
| \[討論\] 板上有人遇過這種情況嗎                                  | 4       | forgetwhat   |
| \[請益\] 在台灣只剩下一年 該換工作嗎?                            | 9       | kissyourbi   |
| \[情報\] (代po)科技人面試求職講座                                | 6       | yunnnn       |
| Re: \[請益\]信鼎技術 面試前準備?                                 | 7       | AlioAlio     |
| Re: \[新聞\] 斥資600億 「綠能科學城」落腳台南沙崙                | 13      | juangpeiyi   |
| \[請益\] offer 選擇                                              | 6       | eclipse911   |
| \[討論\] 系統廠的生命力是否比較強？                              | 8       | join183club  |
| \[請益\] 有人聽過Sogeti這間公司嗎                                | 1       | takeon       |
| \[請益\] offer 選擇                                              | 1       | chrishyper   |
| \[新聞\] 「中國製造2025」美憂威脅國安                            | 12      | AAAB         |
| \[請益\] 菱X科技                                                 | 10      | maxgxking    |
| \[新聞\] 環評空污缺電 黃士修：台積電快走吧!                      | 31      | wahaha23     |
| \[請益\] htc派遣問題                                             |         | seal44       |
| \[新聞\] 傳蔡力行 跳槽聯發科(已公告)                             | 53      | http405      |
| Re: \[新聞\] 傳蔡力行 跳槽聯發科                                 | 10      | jeromeshih   |
| \[新聞\] 聯發科宣布 蔡力行接共同執行長、集團副                   | 72      | RTA          |
| Re: \[請益\] Nvidia的Android Framework/SW Engineer               | 5       | nixt         |
| \[請益\] 敏實集團 minth group                                    | 1       | urocissa     |
| \[聘書\] 研替offer詢問(QNAP/緯創)                                | 5       | lebron0426   |
| Re: \[新聞\] 傳蔡力行 跳槽聯發科(已公告)                         | 15      | TSMCer       |
| \[請益\] 友達 美光 力晶 哪家最推薦去呢?                          | 45      | okopp        |
| \[請益\] 面試請益                                                | 3       | lhx63524     |
| 資料探勘及資料分析的基本能力為何                                 |         | uasalada     |
| \[請益\] 元隆電子                                                | 2       | zyxcba5      |
| \[請益\] FAE面試請益                                             | 30      | lovelyjojo   |
| Re: \[新聞\] 聯發科宣布 蔡力行接共同執行長、集團副               | 14      | a875979      |
| \[請益\] 晶電 vs 鼎元 (竹南)                                     | 9       | kkkmaxtine   |
| \[討論\] 晶睿通訊                                                | 5       | tiyico       |
| \[請益\] gg設備幹到頂天有機會被高薪挖角嗎                        | 4       | onlytiger    |
| \[討論\] 新人離職                                                | 74      | forgood      |
| \[請益\]男生做友達OP 適合待到退休嗎?                             | 19      | Silent       |
| \[討論\] 陣亡率高/免洗的職位                                     | 25      | NTUlosers    |
| \[討論\] 科技業公司一虧損就開始拆子公司是常態嗎                  | 14      | gotptt       |
| \[徵才\] Taylormade Golf company (高雄辦公室)                    |         | loddy        |
| \[討論\] 台積電有可能成為百年企業嗎 ?                            | 9       | goodpoint    |
| \[請益\]華新科福利                                               | 4       | ichior       |
| \[請益\] 緯創server部門好嗎?                                     | 8       | fantacy0225  |
| \[請益\] 尋求找工作方向建議                                      | 2       | YWEC         |
| \[新聞\] 聯發科訂單沒跟上                                        | 3       | unrest       |
| Re: \[討論\] 台積電有可能成為百年企業嗎 ?                        | 6       | bluejade1235 |
| \[新聞\] 聯詠員工分紅打6折 群聯大方送5.5億增1成                  | 6       | gn01216674   |
| \[討論\]報到的第二個禮拜想離職.......                            | 8       | judy79702    |
| Re: \[討論\]報到的第二個禮拜想離職.......                        | 56      | join183club  |
| \[面試\] 在linkedin上找工作 就不會被原公司發現?                  | 5       | sustaned     |
| \[請益\] 錄取未報到..                                            |         | qqdnsr       |
| \[請益\] 首岳資訊網路股份有限公司                                |         | edison81630  |
| Re: \[討論\] 台積電有可能成為百年企業嗎 ?                        | 8       | lovebridget  |
| 長春彰濱廠                                                       | 6       | adidasshow   |
| \[情報\] 英特爾購併Mobileye是追夢還是夢靨？                      | 6       | zxcvxx       |
| Re: \[討論\]報到的第二個禮拜想離職.......                        | 6       | hidog        |
| Re: \[討論\]報到的第二個禮拜想離職.......                        |         | pinkowa      |
| \[請益\] 鴻勝化學&宏騰光電...                                    | 3       | qqming0721   |
| \[討論\] 台塑or中油                                              | 80      | Mason61931   |
| \[新聞\] 蔡力行轉戰聯發科 網友：員工苦日子到                     | 38      | jeromeshih   |
| \[請益\] 英業達Server的power team                                | 4       | middux       |
| \[討論\] 中部某封測廠的面談經驗                                  | 8       | stennis      |
| \[新聞\] 【震驚科技業】蔡力行轉戰聯發科　是否                    | 36      | wahaha23     |
| \[請益\] 奇美材料到底好不好= =                                   | 13      | esp0122      |
| \[請益\] 力晶元件助理工程師                                      | 12      | PTT1774      |
| \[請益\] 大公司的APR 跟小公司的數位IC                            | 17      | qqr29        |
| \[心得\] AMAT/Ultratech/mattson/Rudolph/ASM                      | 25      | roy10531     |
| Fw: \[公司\] 大船集團-達航科技                                   | 3       | Miwaitte     |
| \[請益\] 仁寶 智慧型裝置 android                                 | 12      | jenny920218  |
| \[請益\] 台汽電公司待遇及福利如何                                | 2       | s357678      |
| Re: \[討論\] 台塑or中油                                          | 21      | turn329      |
| \[新聞\] 蔡力行轉戰聯發科 網友：員工苦日子到                     | 22      | cychine      |
| \[請益\] 聯電/美光/友達 選擇                                     | 37      | suryany      |
| \[請益\] 環球水泥與耐落螺絲                                      | 7       | e3472419     |
| Re: \[請益\] 仁寶 智慧型裝置 android                             | 3       | ABCcomputer  |
| \[請益\] 南科 新世紀光電公司好嗎??                               | 6       | zgmfx0326    |
| Re: \[請益\] 環球水泥與耐落螺絲                                  | 4       | giggled      |
| \[討論\] 要求先提供照片 涉及違反就服法???                        |         | seedhyper    |
| Re: \[請益\]信鼎技術 面試前準備?                                 |         | AlioAlio     |
| \[請益\] 克達科技(安捷倫電子量測儀器代理)                        | 2       | dmgucci      |
| \[新聞\] 蔡力行轉戰聯發科 台積電發表看法了                       | 29      | kof70380     |
| \[請益\]請問威剛的工作狀況                                       | 4       | rock913343   |
| \[討論\] 美商Ubiquiti Networks優比快                             | 11      | aaron2034b   |
| Re: \[討論\] 鈞立科技(最新力作再現)                              | 1       | lkklkksppspp |
| \[請益\] C++有沒有類似SCJP的題庫                                 | 5       | Nippey       |

解釋爬蟲結果
------------

``` r
str(dataframeall)
```

    ## 'data.frame':    180 obs. of  3 variables:
    ##  $ Title  : Factor w/ 162 levels "\n\t\t\t\n\t\t\t\t[心得] 船舶暨海洋產業研發中心 面試心得\n\t\t\t\n\t\t\t",..: 10 9 5 13 2 14 16 1 16 11 ...
    ##  $ PushNum: Factor w/ 49 levels "","1","10","14",..: 1 11 1 12 11 11 5 4 8 2 ...
    ##  $ Author : Factor w/ 161 levels "AK47shoot","ccc0901",..: 11 13 2 8 16 17 4 6 3 15 ...

共爬出180篇文章

``` r
sort(table(dataframeall[3]))
```

    ## 
    ##    AK47shoot      ccc0901          cjb       Feases  jason050117 
    ##            1            1            1            1            1 
    ##     kevin505 LibertyWings livefishfish     mimi0213   minwoo0904 
    ##            1            1            1            1            1 
    ##        Moran      nerlens     omes4219     Paravion       s50190 
    ##            1            1            1            1            1 
    ##     SUPER22K         zxlu    a29417557      balzark       BBMADE 
    ##            1            1            1            1            1 
    ##        BCCAT     cacalota Edwardkiller      ggggggh     HateAnus 
    ##            1            1            1            1            1 
    ##  innocentguy  jessicabana       JT0816    kn0105209   LBJ2ndKing 
    ##            1            1            1            1            1 
    ##      lsz6404 schizophrena    smallchou       soufon      starjli 
    ##            1            1            1            1            1 
    ##   unclefucka amethystleaf  charisma007      crafttt     elvisman 
    ##            1            1            1            1            1 
    ##     evil7589  hottea88310       hueepf     kevinZJL    PerfectID 
    ##            1            1            1            1            1 
    ##    popoallan  remember246    rko801024        Sex5F         smst 
    ##            1            1            1            1            1 
    ##   SuperModel     yolosiku     ak080775      ann3222   bboycookie 
    ##            1            1            1            1            1 
    ##   birdhackor  foreverwhat    nomilkman  onlyveritas      pig2014 
    ##            1            1            1            1            1 
    ##     randomly      soaping  terimakasih    TrueSpace   turtle6188 
    ##            1            1            1            1            1 
    ##   typewindow        zaxck   angelpeace      berac16     breath35 
    ##            1            1            1            1            1 
    ##    cliffk321  eraser90310    GameHeven   Intelgence         JE2K 
    ##            1            1            1            1            1 
    ##      kurtgod     lim10337     moonth66      paulu90 qazxc1156892 
    ##            1            1            1            1            1 
    ##   queenghost        wer11         AAAB   chrishyper         DUFA 
    ##            1            1            1            1            1 
    ##   eclipse911   forgetwhat      http405   juangpeiyi   kissyourbi 
    ##            1            1            1            1            1 
    ##   lebron0426    maxgxking         nixt          RTA       seal44 
    ##            1            1            1            1            1 
    ##       takeon     urocissa       yunnnn      a875979  fantacy0225 
    ##            1            1            1            1            1 
    ##      forgood    goodpoint       gotptt       ichior   kkkmaxtine 
    ##            1            1            1            1            1 
    ##     lhx63524        loddy   lovelyjojo    NTUlosers        okopp 
    ##            1            1            1            1            1 
    ##    onlytiger       Silent       tiyico         YWEC      zyxcba5 
    ##            1            1            1            1            1 
    ##   adidasshow bluejade1235      esp0122   gn01216674        hidog 
    ##            1            1            1            1            1 
    ##    judy79702  lovebridget   Mason61931       middux      pinkowa 
    ##            1            1            1            1            1 
    ##      PTT1774       qqdnsr      stennis   aaron2034b  ABCcomputer 
    ##            1            1            1            1            1 
    ##      cychine      dmgucci     e3472419      giggled  jenny920218 
    ##            1            1            1            1            1 
    ##     kof70380 lkklkksppspp     Miwaitte       Nippey        qqr29 
    ##            1            1            1            1            1 
    ##   rock913343     roy10531      s357678    seedhyper      suryany 
    ##            1            1            1            1            1 
    ##      turn329    zgmfx0326       TSMCer     uasalada   appledavid 
    ##            1            1            2            2            2 
    ##        tw689       zxcvxx   qqming0721  edison81630       unrest 
    ##            2            2            2            2            2 
    ##     AlioAlio  join183club  magic704226     wahaha23     sustaned 
    ##            2            2            3            3            3 
    ##   jeromeshih 
    ##            4

前180筆資料顯示作者jeromeshih文章數最多(4篇)

至3月29日，180筆最新文章中『Re: \[請益\] 另一半認為, 7:00下班是不顧家庭』共有12篇文章，表示舊有"女性應該在家帶小孩"的觀念逐漸被挑戰，討論度較高。
