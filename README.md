## 作るスキル (アプリ) 

３つ作ります。

0. 『`ただのオウム返し`』アプリ。ハローワールド
1. 男性・女性の声で『`声変換オウム返し`』スキル
2. 日本語を話しかけたら、英語にして返してくれる『`通訳くん`』スキル。逆も行ける

無料の範囲内でできるスキル。


### １の『オウム返しスキル』ユーザー会話フロー

私「オーケーグーグル、オウム返しくんを起動して」

`『（略）こんにちは、オウム返しくんです。男女どちらの声が良いですか？』`

私「男性」

`『男性の声で復唱します。何か言ってみてください』`

私「ちょまどだよ」

`『ちょまどだよ』`（男性の声）

私「終了」

`『さらばだ』`（ピコン！）


### ２の『通訳くん』ユーザー会話フロー

私「オーケーグーグル、通訳くんを起動して」

`『（略）こんにちは、通訳くんです。通訳したい文章を言ってください』`

私「こんにちは」

`『Hello』`

私「Hello」

`『こんにちは』`

私「終了」

`『さらばだ』`（ピコン！）

## 使用サービス/製品

サービス/製品名|使用目的|提供元
----|----|----
[Microsoft Translator Text API](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview?WT.mc_id=dotnet-0000-machiy)|言語の検出、翻訳|Microsoft
[Microsoft Speech Services API](https://docs.microsoft.com/azure/cognitive-services/speech-service/?WT.mc_id=dotnet-0000-machiy)|テキスト読み上げ (Text to Speech)|Microsoft
[Microsoft Azure Storage](https://docs.microsoft.com/azure/storage/common/storage-introduction?WT.mc_id=dotnet-0000-machiy)|英語の読み上げ音声ファイルの一時保存|Microsoft
[Microsoft Azure Functions](https://docs.microsoft.com/azure/azure-functions/?WT.mc_id=dotnet-0000-machiy)|バックエンド作成（Web サーバー)(サーバーレス)|Microsoft
[Visual Studio Code](https://azure.microsoft.com/products/visual-studio-code/?WT.mc_id=dotnet-0000-machiy)|エディタ (for Windows, macOS, Linux)|Microsoft
[Dialogflow](https://dialogflow.com/)|Google Home や Google アシスタント用の Action (アプリ) を作るときの対話モデル作成|Google
[ngrok](https://ngrok.com/)|localhost で動いているサーバーを外部から叩けるようにする（tunnelling）|ngrok

## アジェンダ

1. 概要説明
    - スマートスピーカー開発概要
    - 今回作るスキルのデモとアーキテクチャ説明
1. 0の『`ただのオウム返しスキル`』ローカルでの動作まで
    - 対話モデルを作る - Dialogflow の設定 (Intent 作成)
    - 動作確認（エミュレータ）- ngrok
1. Azure 導入 (アカウント作成)
1. 1の『`声変換オウム返しスキル`』ローカルでの動作まで
    - Microsoft Speech Services API の Text to Speech REST API のトークン取得
    - バックエンド作成 - Azure Functions with Visual Studio Code
    - 動作確認（エミュレータ）- ngrok
1. Azure にデプロイ
    - クラウド (Azure) にデプロイしてしまえば、実行時にわざわざローカルサーバーを立てる必要が無くなった。いつでもどこでも実行できるよ
    - お手持ちのスマホの Google アシスタントで実行
1. 2の『`通訳くん`』ローカルでの動作まで
    - 対話モデルを作る - Dialogflow の設定 (Intent 作成)
    - Microsoft Translator Text API のトークン取得
    - バックエンド作成 - Azure Functions with Visual Studio Code
    - 動作確認（エミュレータ）- ngrok
1. Azure にデプロイ
    - クラウド (Azure) にデプロイしてしまえば、実行時にわざわざローカルサーバーを立てる必要が無くなった。いつでもどこでも実行できるよ
    - お手持ちのスマホの Google アシスタントで実行


## 題材をこのスキルにした理由

正直、英語にしてくれるスキルは、自分でわざわざオレオレスキルを作らなくてもデフォルトでどの AI アシスタントも持ってるけど、でも自作することによって色々学べるよ！

* 普通にやると、日本語の言語設定にした AI アシスタントには、英文を送っても英語で発音してくれない。なので（翻訳 API の他に）Text to Speech の API をかませる必要がある。
* ハンズオンの題材として、バックエンド主体のスキルにしたいから、何かの API を叩いて情報を引き出す感じのをやりたかった
* このスキルを作る過程で、色々他に応用できるような経験ができる、良い「教材」だと思った
