# About
Yet another open storage of CSV files automatically generated from the association's weekly web announcement, including breakdowns of numbers of visitors and ticket sales for Osaka/Kansai Expo 2025 in Japan.

2025大阪/関西万博の来場者数とチケット販売枚数について、公益社団法人2025年日本国際博覧会協会(以下、協会)が週次でウェブサイト「お知らせ」ページに掲載する運用のようです。このhtmlから取得できるデータを、独自に分解/整理してCSVファイルにします。そして、そのCSVファイルをこのGitHubリポジトリにpushし、公開します。同じCSVファイルを、Google Driveにも同じ階層構造と命名規則で公開します。

## Google Drive
https://drive.google.com/drive/folders/14YngCUtm9Gu-hxWdchokvHy9jgy73XAe
(Notice // 2025/5/24, 13:45 JPT updated / URL changed.)

## folder structure
｜－ misc : tickets / visitors の(当方の行った)整理から(結果的に)外れたもの。例えば、一日券の「超早割」「早割」の内訳(現在、準備中)。

｜－ tickets : チケット販売実績をカンマ区切り、yyyymmdd.txtのファイル名、日次、で更新します。

｜－ visitors : 夢洲への来場者数をカンマ区切り、yyyymm.dd.txtのファイル名、日次、で更新します。


- 協会の更新はこのGitHubリポジトリを開設した2025/5/23現在、毎週月曜日の週次です。しかしながら、自動更新の安定を確認するために、日次更新としています。また、協会の更新曜日が月曜日から変わった場合にも、極力、労力の少ない追随で済むようにという狙い(思い)もあります。

- ファイルの内容は、月曜に当週(前週)分が追加されます。月曜以以外すなわち火曜日から日曜日までは、原則として同じ(更新なし)になります(協会が元のhtmlファイルを変更した場合には、その変更が反映されます)。
