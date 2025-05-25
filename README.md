# About
Yet another open storage of CSV files automatically generated from the association's weekly web announcement, including breakdowns of numbers of visitors and ticket sales for Osaka/Kansai Expo 2025 in Japan.

2025大阪/関西万博の来場者数とチケット販売枚数について、公益社団法人2025年日本国際博覧会協会(以下、協会)が週次でウェブサイト「お知らせ」ページに掲載する運用のようです。このhtmlから取得できるデータを、独自に分解/整理してCSVファイルにします。そして、そのCSVファイルをこのGitHubリポジトリにpushし、公開します。同じCSVファイルを、Google Driveにも同じ階層構造と命名規則で公開します。

## Google Drive
https://drive.google.com/drive/folders/1AkcvZaIz9CP7plRr3DaZ6WrlXpKH0Kgi

-> if 404, please find at https://x.com/copperpan47385 (profile area).

(Notice // 2025/5/25, 02:55am JPT updated / URL changed.)

## folder structure
｜－ misc : tickets / visitors の(当方の行った)整理から(結果的に)外れたもの。例えば、一日券の「超早割」「早割」の内訳(現在、準備中)。

｜－ tickets : チケット販売実績をカンマ区切り、yyyymmdd.txtのファイル名、日次、で更新します。

｜－ visitors : 夢洲への来場者数をカンマ区切り、yyyymm.dd.txtのファイル名、日次、で更新します。


- 協会の更新はこのGitHubリポジトリを開設した2025/5/23現在、毎週月曜日の週次です。しかしながら、自動更新の安定を確認するために、日次更新としています。また、協会の更新曜日が月曜日から変わった場合にも、極力、労力の少ない追随で済むようにという狙い(思い)もあります。

- ファイルの内容は、月曜に当週(前週)分が追加されます。月曜日以外すなわち火曜日から日曜日までは、原則として同じ(更新なし)になります(協会が元のhtmlファイルを変更した場合には、その変更が反映されます)。

## frequency

実行頻度は下のcrontab設定の通り。毎週月曜日の15:30頃が協会の週次更新のタイミングに見えます。

当方はこれを受けて毎週月曜日の15:40-15:55(本番)、16:00-16:15(予備)に週次処理を走らせます。

それ以外も実行しているのは動作確認とテストと、ドキュメントの(都度)更新のためです。

### 月曜日

// 1回目
40 15 * * 1     (本番)毎週月曜日 15:40- html取得と分解再構成

55 15 * * 1     (本番)毎週月曜日 15:55- Google Driveに反映。GitHubに反映

// 2回目
00 16 * * 1     (予備)毎週月曜日 16:00- html取得と分解再構成

15 16 * * 1     (予備)毎週月曜日 16:15- Google Driveに反映。GitHubに反映

### 火曜日から日曜日

// nightly / hourly

30 * * * 2-7    毎時30分にテスト html取得と分解再構成(misc内でのテストを含む)

50 * * * 2-7    毎時50分にテスト Google Driveに反映。GitHubに反映

(GitHubのほうが(どちらかといえば)現状、同期処理がより(即時で)安定しています)

(Google Driveも特に問題のあるわけではなく、google-drive-ocamlfuse の挙動を探りつつ、より効率よく、といったところ)

(Last modified at 19:25pm, 2025/5/25)
