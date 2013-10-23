TC-browser-phone
================
Twilio Clientを利用したブラウザ電話機！

Twilio Clientを使えば皆さんのパソコンも電話機として使う事が可能です。
開発もとっても簡単。

このサンプルコードをダウンロードし、Twilio情報を設定するだけでオッケーです。
カスタマイズはご自由にどうぞ！

Twilioブラウザフォンの動き。
□電話をかける。
画面に表示されている有力欄に下記の形式で電話をかけます。
例) 080xxxxyyyyに電話をかける → +8180xxxxyyyy

・発信ボタンで入力された電話番号に電話をかけます。
・切断ボタンで通話を終了させることが可能です。

□電話をうける。
・Twilioプラウザフォン画面を開いてTwilio電話番号（050）に電話をかけます。
　ブラウザに電話が掛かって来ます。
・切断ボタンで通話を終了させることが可能です。

簡単なファイルの説明。
===========================================================================
index.php
===========================================================================
ブラウザを電話機として開発するためにTwilioで提供しているJS SDKを設定しましょう。
<script type="text/javascript" src="//static.twilio.com/libs/twiliojs/1.1/twilio.min.js"></script>

その後、皆さんのTwilioアカウント情報を設定してください。

・Account SID
・Auth Token
・Twilio APP SID
・Twilio APP name

===========================================================================
TC_BP_TwiML.php
===========================================================================
これがこのブラウザフォンのTwiMLです。
画面から入力された発信先の電話番号は「$_REQUEST['PhoneNumber']」で取得し、
<Dial>の<Number>で電話をかけます。

電話が掛かって来た場合には？
<Dial>の<Client>でTwilio APP nameを設定し、通話を成立させます。
