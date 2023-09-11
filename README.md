# 第５回特別課題
## URLとは  
・インターネット上の住所のようなもの。見たいホームページが「どこにあるファイルか」「どんな名前のファイルか」などを示す情報。  
[URLについて](https://wa3.i-3-i.info/word114.html)  

  ## クエリ文字列とは  
・クエリストリングは通常はURLの末尾に書かれ、最初に「?」をつける。その後は「変数名＝値」の形式で内容を記述していき、さらに変数や値が複数存在する場合は「&」を区切りとして使用する。クエリストリングを使用することで、Webページの表示内容を変化させたり、正確なアクセス解析を行うことが可能。  
[クエリ文字列について](https://ssaits.jp/promapedia/technology/query-string.html)  

## パスパラメーター（パス変数）とは　　
・URLの中の１部分。よくあるのがユーザーIDとか記事IDとか。世の中の様々なサービスでパスパラメータを指定することで特定のユーザーの情報だったり、記事の情報だったりを表示するために活用されている。特徴としてクエリ文字列とは違い**一意なリソースを指定する**/**省略はできない**といったものがある。  
[パスパラメータについて](https://zenn.dev/fujishiro/scraps/3a060b10b17a93)


## クエリ文字列との違いについて
・パスパラメータは特定のもの（画面など）を表示したいときに必要であり、クエリパラメータは特定のもの（画面など）に条件を加える場合に必要。
　つまり**パスパラメーターで表示したい情報を指定していき、更に条件を付け加えたいときはクエリパラメーターでフィルターをかけるようなイメージ**。  
 [パスパラメーターとクエリパラメーターの違いについて](https://zenn.dev/eri_agri/articles/859a3362db8386)  

   ## HTTPメソッドとは  
・ホームページを見るときに使うソフト（Webブラウザ）からホームページのファイルが置いてあるコンピュータ（Webサーバ）に対して出されるお願いの種類  
### GETとは  
WebブラウザからWebサーバに渡す値をURLの後ろにくっつけて送るやり方であり意味としては**このページをくれよというお願い**  

### POSTとは  
WebブラウザからWebサーバに渡す値を見えないところにくっつけて送るやり方であり意味としては**このデータをやるから追加しとけというお願い**  
※GETメソッドはページなどを受け取るために使う。POSTメソッドは会員登録の情報などをサーバーに送るために使う。  

### PUTとは  
**今、送ったファイルなんだけどさ。そっちになかったら置いてよ。すでにあったら置き換えてよというお願い**  
※POST違いデータが既存の場合上書きされていく  

### PATCHとは　　
データがすでに存在しているものに対して更新をかける処理。  
PUTはデータが存在する場合はデータが存在しない場合は新規作成を行う。PATCHはデータが存在している時のみ行える。  

### DELETEとは　　
**今、指定したファイルなんだけどさ。サクっと消しちゃってよ！なお願い**  
サーバー上のファイルなどの削除を行う操作。サーバがクライアントにデータやサービスを提供する一般的なWebサイトで使われることは稀。  

[GET/POST](https://wa3.i-3-i.info/word110431.html)・[PUT](https://e-words.jp/w/PUT%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89.html)・[PATCH](https://omathin.com/http-method/)・[DELETE](https://e-words.jp/w/DELETE%E3%83%A1%E3%82%BD%E3%83%83%E3%83%89.html)  

  ## HTTPステータスコードとは  
・ホームページを見るときに使うソフト（Webブラウザ）からホームページのファイルが置いてあるコンピュータ（Webサーバ）に対して出される「このページをちょうだい」なお願いに対する**Webサーバさんからの返事を表した3桁の数字**  
[HTTPステータスコードについて](https://wa3.i-3-i.info/word166.html)  


| HTTPSステータスコード | ステータスコードの意味 |
| :-------------| :------------------|
|200            |リクエストが正常に処理できた|
|201            |リクエストが成功してリソースの作成が完了|
|400            |一般的なクライアントエラー|
|404            |Webページが見つからない|
|500            |何らかのサーバ内で起きたエラー|

## リクエストヘッダーとは・リクエストボディとは    
### リクエストヘッダー  
  ⇨ホームページを見るときに使うソフト（Webブラウザ）からホームページのファイルが置いてあるコンピュータ（Webサーバ）に伝えたい「お願いごとやお願い元に関するあれこれ」が書かれている場所  
### リクエストボディ    
  ⇨「補足のメモ書き情報」が書かれている場所

1. HTTPリクエストライン（リクエストライン）[^1]  
1. HTTPリクエストヘッダ（ヘッダ）[^2]  
1. HTTPリクエストメッセージボディ（メッセージボディ）[^3]  

[^1]:POST /search.html HTTP/1.1\r\n  
[^2]:Host: wa3.i-3-i.info\r\n   
Connection: keep-alive\r\n  
Content-Length: 38\r\n  
Cache-Control: max-age=0\r\n  
Origin: http://wa3.i-3-i.info\r\n  
Upgrade-Insecure-Requests: 1\r\n  
User-Agent: うんちゃら\r\n  
Content-Type: application/x-www-form-urlencoded\r\n  
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/webp,image/apng,*/*;q=0.8\r\n  
Referer: http://wa3.i-3-i.info/index.html\r\n  
Accept-Encoding: gzip, deflate\r\n  
Accept-Language: ja,en-US;q=0.8,en;q=0.6\r\n 
[^3]:\r\n  
q=test&submitSearch=%E6%A4%9C%E7%B4%A2  

  
[HTTPステータスコードについて](https://www.itmanage.co.jp/column/http-www-request-response-statuscode/)  


  ## レスポンスヘッダー・ボディとは  
  ### レスポンスヘッダー  
  　　⇨「HTTPステータスラインに書ききれないレスポンスの情報」が書かれている場所  
  ### レスポンスボディ  
  　　⇨「相手が欲しがってたファイルの中身」が書かれている場所  

1. HTTPリクエストライン（ステータスライン）[^4]  
1. HTTPレスポンスヘッダ（ヘッダ）[^5]  
1. HTTPレスポンスボディ（レスポンスボディ）[^6]

[^4]:HTTP/1.1 200 OK\r\n  
[^5]:Server: nginx\r\n  
Date: Tue, 11 Jul 2017 09:23:07 GMT\r\n  
Content-Type: text/html\r\n  
Transfer-Encoding: chunked\r\n  
Connection: keep-alive\r\n  
\r\n  
[^6]:\r\n~


  
    
## JSONとは  
  ・JavaScriptと相性が良いファイルの書き方ルールのひとつ  

    
  ![image](https://github.com/yuu3415/specialhomework/assets/143332858/e2ac6c9e-555f-465f-bcdd-d40a080da3fc)  

  ```Swift
  {
  "color_list": [ "red", "green", "blue" ],
  "num_list": [ 123, 456, 789 ],
  "mix_list": [ "red", 456, null, true ],
  "array_list": [ [ 12, 23 ], [ 34, 45 ], [ 56, 67 ] ],
  "object_list": [
    { "name": "Tanaka", "age": 26 },
    { "name": "Suzuki", "age": 32 }
  ]
}
```
  
  
  



