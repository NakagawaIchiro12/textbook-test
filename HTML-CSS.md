# 自己紹介ページを作ります。

![img00](https://job555.info/wp-content/uploads/2020/04/img00.png)

上記のような自己紹介ページをAtomエディタを使って作ることができます。

## 下準備をします。

Atomエディタの画面上のナビゲーションメニューから、

ファイル＞プロジェクトフォルダを追加（別ウインドウが開きます）＞
（別ウインドウの左下）新規作成（名前をhtmlcss-work)＞の順に

新しく「htmlcss-workファイル」を作成します。


その中に演習用素材からダウンロードした素材を入れてください。

### ダウンロードページ
https://job555.info/html-css/

ダウンロードページのパスワード：htmlcss

入れる素材は
1. header-bg.jpg
2. profile2.jpg

の２点です。

素材をダウンロードし、ドラッグ&ドロップでhtmlcss-workのフォルダに入れ、
アップロードします。

素材のダウンロードは下記リンクからダウンロードすることができますし、
自分で用意しても大丈夫です。
（自分で用意した方は、ファイル名と、ファイルのサイズを揃えておくと
今後の作業が進めやすいと思います。）

##### ファイル名とファイルサイズ
- header-bg.jpg
  - ファイルサイズ : 1705px x 544px
- profile2.jpg
  - ファイルサイズ : 500px x 500px

## 自己紹介ページのHTMLを作成します。
### 先ほど作成したhtmlcss-workのフォルダに、mysite.htmlを作成します。
htmlcss-workフォルダ上で右クリック＞新規ファイル＞htmlcss-work/mysite.html
の順で作成します。

では作っていきましょう。
まず、　半角で　「!」　を入力し、tabキーを入力することで、下記の内容が自動で入力されます。

```html:mysite.html
    <!DOCTYPE html>
    <html lang="en">
    <head>
      <meta charset="UTF-8">
      <meta name="viewport" content="width=device-width, initial-scale=1.0">
      <meta http-equiv="X-UA-Compatible" content="ie=edge">
      <title>Document</title>
    </head>
    <body>

    </body>
    </html>
```

このページでは、全てmysite.htmlにコードを書いていきます。

次に、メタタグを２行削除します。
削除するのは下記の２行です。
headタグの下にmetaタグが３行あります。そのうちの下２行です。

```html:mysite.html
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
```

そして、２行目のhtml lang="en"　をhtml lang="ja"に変更し、ホームページの言語の属性を英語→日本語に変更します。

そして、５行目のtitleタグを　Document→自己紹介ページ　に変更します。

bodyタグの中に hello world　と記入してみましょう
previewタブの画面には　「hello world」と表示だけされたはずです。

ここまでのコードは以下の通りになりました。

```html:mysite.html
    <!DOCTYPE html>
    <html lang="ja">
    <head>
      <meta charset="UTF-8">
      <title>自己紹介ページ</title>
    </head>
    <body>
    hello world
    </body>
    </html>
```

### ここまで行なった作業は以下の通り
- メタタグを２行削除
- html langを　en から　ja　に変更
- titleタグを　Document　から　自己紹介ページ　に変更
- bodyタグ内に hello world　と入力し、Previewタブで　hello world　と表示


### ここまでで、自己紹介ページの下準備ができました。
***
## ここからはヘッダー部分のHTMLを作っていきます。

ではまずbodyタグ内にヘッダータグを入力していきます。

```html:mysite.html
    <body>
      <header>

      </header>
    hello world
    </body>
```

 そしてその中にdivタグを作ってまとまりを作っていきます。

```html:mysite.html
     <body>
       <header>
          <div>

          </div>
       </header>
     hello world
     </body>
```

 **そのdivタグにはtopというクラスをつけておきます。**

```html:mysite.html
     <body>
       <header>
          <div class="top">

          </div>
       </header>
     hello world
     </body>
```


このように記述してみてください。

そして、プロフィール画像を貼り付けていきます。
先ほどのdiv class="top"タグの中に下記のコードを入力します。
id="icon"　の目印をつけて、あとでデザインしやすいようにします。


```html:mysite.html
    <img src="profile.jpg" id="icon">
```

imgタグの次に入力するのが、名前になります。
名前はspanタグで作ってみましょう。

```html:mysite.html
    <span id="myname">中川　いちろう</span>
```


その次に書くのが、ナビゲーションです。
自分のブログや、Twitter、Instagram、Facebookにリンクできるようにします。

```html:mysite.html
    <nav>
      <ul>
        <li>blog</li>
        <li>Twitter</li>
        <li>Instagram</li>
        <li>Facebook</li>
      </ul>
    </nav>
```

ここまで記載することで、
- blog
-Twitter
-Instagram
-Facebook

とリスト形式になっているのがわかるのではないでしょうか。
ではこのリストに、aタグをつけてリンクにしていきましょう

    blogを<a hred="#">blog</a> のように囲みます。
他も同じように囲みましょう。


```html:mysite.html
    <nav>
      <ul>
        <li><a href="https://job555.info">blog</a></li>
        <li><a href="https://twitter.com/nobuyasai2">Twitter</a></li>
        <li><a href="https://www.instagram.com/ichiro.nobuyasai/">Instagram</a></li>
        <li><a href="https://www.facebook.com/nakagawa.ichiro">Facebook</a></li>
      </ul>
    </nav>
```

こうすることで、リンクになります。
しかし、このリンクをクリックした後このページには戻ってこないことが
多いと思います。

それでは、このページをしっかりみてもらえないので
リンクをクリックした時に、別ウインドウで開くようにします。

```html:mysite.html
    <a href="https://job555.info" target="_blank">blog</a>
```

と上記のように、　target="_blank" を追加します。必ず前の記述から
半角スペースが入っているように注意して入力してください。

```html:mysite.html
    <nav>
      <ul>
        <li><a href="https://job555.info" target="_blank">blog</a></li>
        <li><a href="https://twitter.com/nobuyasai2" target="_blank">Twitter</a></li>
        <li><a href="https://www.instagram.com/ichiro.nobuyasai/" target="_blank">Instagram</a></li>
        <li><a href="https://www.facebook.com/nakagawa.ichiro" target="_blank">Facebook</a></li>
      </ul>
    </nav>
```

これで、blog,twitter,instagram,facebookの4つとも、新しい
ページで開くようになりました。

これで、ページのヘッダーの部分を作ってきましたので、
次回で、ページの中身を作っていきます。

### ここまででできたコードはこんな感じです。

```html:mysite.html
    <!DOCTYPE html>
    <html lang="ja">
    <head>
      <meta charset="UTF-8">
      <title>自己紹介ページ</title>
    </head>
    <body>
      <<header>
        <div class="top">
          <img src="profile2.jpg" id="icon">
          <span id="myname">中川　いちろう</span>
          <nav>
            <ul>
              <li><a href="https://job555.info" target="_blank">blog</a></li>
              <li><a href="https://twitter.com/nobuyasai2" target="_blank">Twitter</a></li>
              <li><a href="https://www.instagram.com/ichiro.nobuyasai/" target="_blank">Instagram</a></li>
              <li><a href="https://www.facebook.com/nakagawa.ichiro" target="_blank">Facebook</a></li>
            </ul>
          </nav>
        </div>
      </header>
    hello world
    </body>
    </html>
```


# 中身の部分とフッターの部分を作成していきます。

headerタグの下に、divタグでまとまりを作っていきます。
divタグにcontainerとidをつけることで、まとまりにします。

```html:mysite.html
    <div class="container">

    </div>
```

そしてそのcontainerクラスの中に、h2タグで囲んで「自己紹介」
とタイトルをつけます。

```html:mysite.html
    <div class="container">
      <h2>自己紹介</h2>

    </div>
```

そして、自己紹介の下に、またdivタグでまとまりを作ります。
クラス名はprofileとします。/divの閉じタグも、divタグを作るときは
常に忘れないようにしましょう。

```html:mysite.html
    <div class="container">
      <h2>自己紹介</h2>
        <div class="profile">

        </div>
    </div>
```


これで、div class="container"のかたまりの中に、
div class="profile"のかたまりができました。

その中に、pタグを使って、自分の自己紹介文を書いていきましょう。

```html:mysite.html
    <p>愛知県で初の有機JASニンジンを作り、高級スーパーフランテ２４店舗に流通。
    年間1200人が受講する「健康セミナー」と有機JASニンジンのコラボ「家族で遊ぶ収穫祭」を10年開催中
    副業のアフィリエイトで月収10万円を達成、Webディレクターとして
    として個人で営業し、ホームページ制作を受注。
    1986年10月16日生まれ
    愛知県出身
    名古屋経済大学管理栄養学科</p>
```


自己紹介を書いたpタグを　div class="profile"の中に入れます。
見にくければ改行しちゃってください。HTML上で改行しても、見た目には反映されないので大丈夫です。
もちろん最初にpタグを作成し、自己紹介を書いていく順番でも
大丈夫です。

```html:mysite.html
    <div class="container">
      <h2>自己紹介</h2>
        <div class="profile">
          <p>愛知県で初の有機JASニンジンを作り、高級スーパーフランテ２４店舗に流通。
          年間1200人が受講する「健康セミナー」と有機JASニンジンのコラボ「家族で遊ぶ収穫祭」を10年開催中
          副業のアフィリエイトで月収10万円を達成、Webディレクターとして
          として個人で営業し、ホームページ制作を受注。
          1986年10月16日生まれ
          愛知県出身
          名古屋経済大学管理栄養学科</p>
        </div>
    </div>
```


このようになりますね。
毎回、インデントを整えることも忘れないでください。

実際のHTMLで改行するためにはbrタグを入れます。
今回はbrタグを2つ挿入することにします。

```html:mysite.html
    <div class="container">
      <h2>自己紹介</h2>
        <div class="profile">
          <p>愛知県で初の有機JASニンジンを作り、高級スーパーフランテ２４店舗に流通。
          <br>
          年間1200人が受講する「健康セミナー」と有機JASニンジンのコラボ「家族で遊ぶ収穫祭」を10年開催中
          <br>
          副業のアフィリエイトで月収10万円を達成、Webディレクターとして
          として個人で営業し、ホームページ制作を受注。
          1986年10月16日生まれ
          愛知県出身
          名古屋経済大学管理栄養学科</p>
        </div>
    </div>
```


ここまで入力すると、Previewでは次のようになっていると思います。
![img01](https://job555.info/wp-content/uploads/2020/04/img01.png)

少し見にくいので、自己紹介文と生年月日の間に水平線を入れましょう。

水平線はhrタグです。

ついでに、生年月日の下にもbrタグを2つ入れて読みやすくします。

```html:mysite.html
    <div class="container">
      <h2>自己紹介</h2>
        <div class="profile">
          <p>愛知県で初の有機JASニンジンを作り、高級スーパーフランテ２４店舗に流通。
          <br>
          年間1200人が受講する「健康セミナー」と有機JASニンジンのコラボ「家族で遊ぶ収穫祭」を10年開催中
          <br>
          副業のアフィリエイトで月収10万円を達成、Webディレクターとして
          として個人で営業し、ホームページ制作を受注。
          <hr>
          1986年10月16日生まれ
          <br>
          愛知県出身
          <br>
          名古屋経済大学管理栄養学科</p>
        </div>
    </div>
```

すると、このようになりました。
![img02](https://job555.info/wp-content/uploads/2020/04/img02.png)

かなり見やすく改行されましたね！

生年月日の部分をbrタグで改行しましたが、若干狭すぎます。
brタグをやめて、１行ずつpタグで囲んでみましょう。

```html:mysite.html
    <div class="container">
      <h2>自己紹介</h2>
        <div class="profile">
          <p>愛知県で初の有機JASニンジンを作り、高級スーパーフランテ２４店舗に流通。
          <br>
          年間1200人が受講する「健康セミナー」と有機JASニンジンのコラボ「家族で遊ぶ収穫祭」を10年開催中
          <br>
          副業のアフィリエイトで月収10万円を達成、Webディレクターとして
          として個人で営業し、ホームページ制作を受注。
          <hr>
          <p>1986年10月16日生まれ</p>
          <p>愛知県出身</p>
          <p>名古屋経済大学管理栄養学科</p></p>
        </div>
    </div>
```


最後の大学の部分にpの閉じタグが2つ重なってしまいました。
これでは見た目も良くないので、hrタグの前にカットしてペーストします。

```html:mysite.html
    <div class="container">
      <h2>自己紹介</h2>
        <div class="profile">
          <p>愛知県で初の有機JASニンジンを作り、高級スーパーフランテ２４店舗に流通。
          <br>
          年間1200人が受講する「健康セミナー」と有機JASニンジンのコラボ「家族で遊ぶ収穫祭」を10年開催中
          <br>
          副業のアフィリエイトで月収10万円を達成、Webディレクターとして
          として個人で営業し、ホームページ制作を受注。
          </p>
          <hr>
          <p>1986年10月16日生まれ</p>
          <p>愛知県出身</p>
          <p>名古屋経済大学管理栄養学科</p>
        </div>
    </div>
```

これでキレイに整いました。
これで、水平線の下に、誕生日と、出身地と所属していた大学がわかるようになりました。

## 最後にフッターを作ります。

今まで作ってきたdiv class="container"というクラスが、
自己紹介サイトの本文になっています。
その下に、フッターを作っていくことになります。

ですので、div class="container"の閉じタグの下から
フッタータグを入力していきましょう。

入力するフッタータグは以下の通りです。

```html:mysite.html
    <footer>
    <p>Nakagawa ichiro</p>

    </footer>
```

こんな感じです。
実際に入力するとこうなります。

```html:mysite.html
    <div class="container">
      <h2>自己紹介</h2>
        <div class="profile">
          <p>愛知県で初の有機JASニンジンを作り、高級スーパーフランテ２４店舗に流通。
          <br>
          年間1200人が受講する「健康セミナー」と有機JASニンジンのコラボ「家族で遊ぶ収穫祭」を10年開催中
          <br>
          副業のアフィリエイトで月収10万円を達成、Webディレクターとして
          として個人で営業し、ホームページ制作を受注。
          </p>
          <hr>
          <p>1986年10月16日生まれ</p>
          <p>愛知県出身</p>
          <p>名古屋経済大学管理栄養学科</p>
        </div>
    </div>
    **ここからフッタータグをスタートします。**
    <footer>
    <p>Nakagawa ichiro</p>

    </footer>
```

フッターの部分にはコピーライトといって、このページの
著作権は私にありますよ。という表示になっています。

コピーライトは &copy; を名前の前に入力します。
;の後に半角スペースを入れて、ちょうどいい隙間を空けておきましょう。

```html:mysite.html
    <footer>
    <p>&copy; Nakagawa ichiro</p>

    </footer>

```

このように著作権のマークと自分の名前が表示されました。

現段階では一切デザインをしていないので、見た目は整っていません。


ここまで行ったことを改めて構造を確認してみると
- 画像と、自分の名前があります。
- その下に、リンク集がリスト形式で存在しています。
- その下に、h2タグで自己紹介と書いてあり、div class="container"に本文が書いてあります。
- その下に、footerタグの中に、著作権マークとウェブサイト作成者の名前があります。

ここからCSSを使ってデザインを当ててみましょう。
### CSSを使うための準備をします。

- htmlcss-workフォルダを右クリックし、
![フォルダクリックimg03](https://job555.info/wp-content/uploads/2020/04/img03.png)
- 新規ファイルを作成をクリックし、
![名前を入力img04](https://job555.info/wp-content/uploads/2020/04/img04.png)
- mysite.cssと入力し、エンターキーでCSSファイルを作ります。
![mysite.cssを開くimg05](https://job555.info/wp-content/uploads/2020/04/img05.png)
そうしたら、mysite.htmlとmysite.cssを
リンクするために、headタグの中にlinkタグを記入します。

```html:mysite.html
    <link rel="stylesheet" href="mysite.css" type="text/css" />
```

入力すると、下記のようになります。

```html:mysite.html
    <head>
      <link rel="stylesheet" href="mysite.css" type="text/css" />
      <meta charset="UTF-8">
      <title>自己紹介ページ</title>
    </head>
```

これで、CSSでデザインしていく準備が整いました。

最後に、ここまで書いてきたコードを確認しておきましょう。

```html:mysite.html
    <!DOCTYPE html>
    <html lang="ja">
    <head>
      <link rel="stylesheet" href="mysite.css" type="text/css" />
      <meta charset="UTF-8">
      <title>自己紹介ページ</title>
    </head>
    <body>
      <header>
        <div class="top">
          <img src="profile2.jpg" id="icon">
          <span id="myname">中川　いちろう</span>
          <nav>
            <ul>
              <li><a href="https://job555.info" target="_blank">blog</a></li>
              <li><a href="https://twitter.com/nobuyasai2" target="_blank">Twitter</a></li>
              <li><a href="https://www.instagram.com/ichiro.nobuyasai/" target="_blank">Instagram</a></li>
              <li><a href="https://www.facebook.com/nakagawa.ichiro" target="_blank">Facebook</a></li>
            </ul>
          </nav>
        </div>
      </header>
      <div class="container">
        <h2>自己紹介</h2>
          <div class="profile">
            <p>愛知県で初の有機JASニンジンを作り、高級スーパーフランテ２４店舗に流通。
            <br>
            年間1200人が受講する「健康セミナー」と有機JASニンジンのコラボ「家族で遊ぶ収穫祭」を10年開催中
            <br>
            副業のアフィリエイトで月収10万円を達成、Webディレクターとして
            として個人で営業し、ホームページ制作を受注。
            <hr>
            <p>1986年10月16日生まれ</p>
            <p>愛知県出身</p>
            <p>名古屋経済大学管理栄養学科</p></p>
          </div>
      </div>
      <footer>
      <p>&copy; Nakagawa ichiro</p>

      </footer>
    hello worlds
    </body>
    </html>
```

見た目はこんな感じになっていると思います。

![HTML完成img06](https://job555.info/wp-content/uploads/2020/04/img06.png)

/footerの下のhello worldを消して、「お問い合わせはTwitterからどうぞ！」と記載し、HTMLは完成です。
＊このお問い合わせの部分は、自分のお問い合わせが受けやすいSNSでいいと思います。
＊リンクはご自身のものを使ってください。

```
  <footer>
    <p>&copy; Nakagawa ichiro</p>
    <p>お問い合わせは<a href="https://twitter.com/nobuyasai2" target="_blank">Twitter</a>からどうぞ</p>
  </footer>
  </body>
  </html>
```


### 最後に、できたHTMLファイルを実際のWebブラウザで確認してみよう！
Atomエディタタブの一番左側、projectタブから、作成したHTMLファイル
今回は「mysite.html」を右クリックし、Finderから開くを選択します。
![img07](https://job555.info/wp-content/uploads/2020/04/img07.png)

すると、下記画面が開きます
![img08](https://job555.info/wp-content/uploads/2020/04/img08.png)

Finderのウインドウから、「mysite.html」を右クリックし、
このアプリケーションで開く＞Google Chrome　をクリックします。

＊Google Chromeブラウザをインストールしていない方は、この際にインストールしておきましょう。

![img09](https://job555.info/wp-content/uploads/2020/04/img09.png)

すると、Webブラウザでmysite.htmlが表示されました。
![img10](https://job555.info/wp-content/uploads/2020/04/img10.png)

これで、見たいHTMLファイルをブラウザで見ることができるようになりました！
AtomエディタのPreview表示も超ベンリですが、
実際のWebブラウザで確認することも大切になってきます。

## HTMLはここで完成です！次はCSS編で自己紹介ページにSNS風のデザインを当てていきましょう！
