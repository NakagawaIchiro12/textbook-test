## CSSでデザインを当てていきましょう

これから、mysite.cssを書いていくことで、デザインを
当てていくことになります。

*前回のHTML編の最後でhtmlファイルとcssファイルのリンクの方法を書いてありますので、
リンクできていない方はそちらをみてリンクをしてから初めてください。


では、ヘッダーの背景画像を当てていくところから始めましょう。

ヘッダーの背景画像を変えていくには、cssに以下のように書いていきます。

```css:mysite.css
    header{
      background-img: url("/Users/ritsuko/Desktop/server/Atom/htmlcss-work/header-bg.jpg");

    }
```

では、CSSからはWebブラウザで反映を確認していきましょう。

### 前回作ったHTMLファイルを実際のWebブラウザで開きます。
Atomエディタタブの一番左側、projectタブから、作成したHTMLファイル
今回は「mysite.html」を右クリックし、Finderから開くを選択します。
![img07](https://job555.info/wp-content/uploads/2020/04/img07.png)

すると、下記画面が開きます
![img08](https://job555.info/wp-content/uploads/2020/04/img08.png)

Finderのウインドウから、「mysite.html」を右クリックし、
このアプリケーションで開く＞Google Chrome　をクリックします。


![img09](https://job555.info/wp-content/uploads/2020/04/img09.png)

すると、Webブラウザでmysite.htmlが表示されました。
![img10](https://job555.info/wp-content/uploads/2020/04/img10.png)

これで、見たいHTMLファイルをブラウザで見ることができるようになりました！
## CSSを書いた後、デザインの反映を確認する方法
- mysite.cssを保存
- 先ほど立ち上げておいたmysite.htmlが表示されたGoogle Chromeを更新
- これでCSSの更新を毎回見ることができます。

#### もし間違えてブラウザを消してしまっても、同じ手順で確認画面を開くことができます。

では続きをやっていきましょう。
headerの背景画像を挿入しました。しかし、まだデザインがうまくできていません。
![img-css01](https://job555.info/wp-content/uploads/2020/04/img-css01.png)

これはbackgroundのサイズを指定していないから起こる問題で、これから解決していきます。
#### 背景画像の繰り返しを防ぐ

```css:mysite.css
    background-size: cover;
```

を追加します。保存をし、更新をすると、繰り返しを防ぎました。

#### 背景画像の周りの白い余白を消す
デフォルトで、周りに若干の余白が定義されています。
これをマージンと言います。
マージンを０にして、なくしてしまいましょう。

headerの前に、マージンを定義します。

```css:mysite.css
    *{
    margin: 0;
    padding: 0;
    }
```

これで、headerの背景画像の周りの余白も無くなりました。
![img-css02](https://job555.info/wp-content/uploads/2020/04/img-css02.png)
ここまでのCSSのコードは以下の通りになっています。

```css:mysite.css
    *{
    margin: 0;
    padding: 0;
    }

    header{
      background-image:url(/Users/ritsuko/Desktop/server/Atom/htmlcss-work/header-bg.jpg);
      background-size: cover;
    }
```

#### もしうまくできていない場合は、
問題点として
- 半角スペースを入れるところが全角スペースになっている
- :（コロン）と；（セミコロン）の打ち間違いがある
- headerを　haedrと入力するなどの入力ミスがある

これが初歩的なミスとしてあるので、チェックしてみましょう。

#### 問題点を予測する方法
チェック方法として、上のコードをコピペしてみるという方法があります。
それで動けば、コードが間違っていますし、
それでも動かなければ、リンクがうまくいっていないのだろうと
問題点を予測することができます。

#### では次に、bodyの背景色に、緑色を当てていきましょう。
headerのCSSの下に、下記コードを書いてみましょう。


```css:mysite.css
    body{
      background-color: #ddffcc;
    }
```

グーグルで実際のカラーコードを　#ddffcc  と検索すると、色が出てきます。
ここで好みのカラーを簡単に見つけることもできるので、使ってください。

それでは保存してもらって、自己紹介ページをみてみてください。
黄緑色の背景色が適用されているのがわかります。

![img-css03](https://job555.info/wp-content/uploads/2020/04/img-css03.png)

#### 自分のアイコンが大きすぎるので、サイズを変えます。

このままではサイズが大きすぎるので、サイズを変えていきましょう。

この画像には、id=iconというのが付いています。
プロフィール画像のサイズを150pxに指定します。
bodyのCSSの下に、コードを書いていきます。

```css:mysite.css
    #icon{
    width: 150px;
    }
```

すると、下のサイズになります。

![img-css04](https://job555.info/wp-content/uploads/2020/04/img-css04.png)

##### このままではアイコンがみにくいので、白い線を入れていきます。
#iconのCSSに追加していきます。

```css:mysite.css
    #icon{
    width: 150px;
    border: solid white;
    }
```

すると、白い線が引かれます。

##### 角も丸くしましょう。

CSSプロパティを書いていきます。
border: solid white;の下に追記していきます。

```css:mysite.css
    border-radius: 10%;
```

![img-css-05](https://job555.info/wp-content/uploads/2020/04/img-css05.png)
今回は10%ですが、50%にすると、丸になります。
試してみてください。
#iconのCSSは下記の通りになりました。

```css:mysite.css
    #icon{
    width: 150px;
    border: solid white;
    border-radius: 10%;
    }
```

### 自分の名前を白文字で目立たせます。
htmlファイルを見てみると、名前のところは

```css:mysite.css
    <span id="myname">中川　いちろう</span>
```


と記述されており、id="myname"というのが付いています。

ですので、CSSファイルでは#mynameで作り、色と文字の大きさを変えます。
- colorがWhite（白）
- font-sizeが40px(大きさ)
- font-weightがbold(太さ)

を入力していきます。

```css:mysite.css
    #myname{
      color: white;
      font-size: 40px;
      font-weight:bold;
    }
```


![img-css06](https://job555.info/wp-content/uploads/2020/04/img-css06.png)

さらに、文字をもっとかっこよくします。

##### 文字に影をつけましょう。

#mynameに追加します。

```css:mysite.css
    text-shadow: 2px 2px 1px black;
```

ちなみに、この数値を変えると、影の大きさや位置を変えることができます。
詳しく知りたい方はtext-shadowで検索してみてください！

![img-css07](https://job555.info/wp-content/uploads/2020/04/img-css07.png)

これでかっこよくなりましたね！
#mynameのCSSは以下のようになりました。

```css:mysite.css
    #myname{
      color: white;
      font-size: 40px;
      font-weight:bold;
      text-shadow: 2px 2px 1px black;
    }
```

## ここまででCSSは下記のようになりました。

```css:mysite.css
    *{
      padding: 0;
      margin: 0;
    }

    body{
      background-color: #ddffcc;
    }

    #icon{
    width: 150px;
    border: solid white;
    border-radius: 10%;
    }

    #myname{
      color: white;
      font-size: 40px;
      font-weight:bold;
      text-shadow: 2px 2px 1px black;
    }

    header{
      background-image:url(/Users/ritsuko/Desktop/server/Atom/htmlcss-work/header-bg.jpg);
      background-size: cover;
    }
```

### ナビゲーションバーをデザインしていきます。

ナビゲーションバーはnavというのが付いています。
CSSに記入していきます。
##### ナビゲーションバーの背景色を変えます。
headerの下に書いていきましょう。

```css:mysite.css
    nav{
    background-color: #aacccc;
    }
```

CSSに記入しセーブして、ブラウザを更新します。

すると、blog twitter Instagram Facebookのナビゲーションの
色が変わっています。

![img-css08](https://job555.info/wp-content/uploads/2020/04/img-css08.png)

### ナビゲーションバーの要素を横並びにします。
##### blog twitter Instagram Facebookのナビゲーションを縦から横に揃える方法です。
ナビゲーションバーのHTMLは、下記のようになっています。

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

      この　<li>　はブロック要素の
      タグなので、自動で改行が入ってしまうわけです。

      改行を入れないようにするためには、
      小さな要素として扱うインライン要素として
      デザインで見せてあげればいいです！

      そのため、<nav>の下の<ul>の下の<li>に対して
      CSSを書きます。
では実際に書いてみます。

CSSのnavの下に書いていきます。

```css:mysite.css
    nav ul li{
        display: inline;
    }
```

![img-css09](https://job555.info/wp-content/uploads/2020/04/img-css09.png)
このように、横並びに変えることができました。

##### ナビゲーションバーにもう少しマージンをつけて見栄えよくしましょう
nav ul liの続きを書いていきます。

```css:mysite.css
    margin: 0 15px 0 15px;
```

![img-css10](https://job555.info/wp-content/uploads/2020/04/img-css10.png)

これで、間隔が見栄えよくなりました。
マージンの数字の順番についてはmarginで検索してみてください。


##### ナビゲーションバーのリンクの下線を消します。
リンクは aタグが割り当てられています。
a href="https://job555.info"　の 最初のaのことです。

```html:mysite.html
    <li><a href="https://job555.info" target="_blank">blog</a></li>
このaタグの位置はというと・・・・

    <nav>
      <ul>
        <li><a href="https://job555.info" target="_blank">blog</a></li>
        <li><a href="https://twitter.com/nobuyasai2" target="_blank">Twitter</a></li>
        <li><a href="https://www.instagram.com/ichiro.nobuyasai/" target="_blank">Instagram</a></li>
        <li><a href="https://www.facebook.com/nakagawa.ichiro" target="_blank">Facebook</a></li>
      </ul>
    </nav>

    <nav>の下の<ul>の下の<li>の下の<a>
    ということになるので・・・
```

CSSに記述するのは、下記を書いていきます。
text decorationが、リンクの下線で、noneがなしです。

```css:mysite.css
    nav ul li a{
        text-decoration: none;
    }
```

![img-css11](https://job555.info/wp-content/uploads/2020/04/img-css11.png)

これで、リンクの下線がなくなりました。


##### ナビゲーションの文字の色と、太さを変えます。

先ほどの nav ul li aに追加していきます。

```css:mysite.css
    color: #444444;
    font-weight: bold;
```

だいぶかっこよくなってきましたね！

nav ul li a のCSSはこのようになりました。

```css:mysite.css
    nav ul li a{
        text-decoration: none;
        color: #444444;
        font-weight: bold;
    }
```


![img-css12](https://job555.info/wp-content/uploads/2020/04/img-css12.png)

##### サイトを中央揃えにします。

headerがどのようなHTMLで作られていたかというと

div class="top"というのがついています。

なので、このtopというのを中央にします。
そうすることで、headerの中身を中央に揃えることができます。

```html:mysite.html
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
```

どのように記述するかというと

##### まず、幅を決めます。

```css:mysite.css
    .top{
    width: 800px
    }
```

![img-css13](https://job555.info/wp-content/uploads/2020/04/img-css13.png)

##### 中央に揃えます。

```css:mysite.css
    .top{
        width: 800px;
        margin: 0px auto 0px auto;
    }
```

![img-css14](https://job555.info/wp-content/uploads/2020/04/img-css14.png)
このように、中央に寄せることができました。
なぜautoにしたかというと、今回は中央に寄せたかったので、
左から●●px、右から●●pxと指定できません。

上下は0pxで大丈夫です。

画面のサイズによって変わってしまうからです。

###### ですから、左をauto,右をautoにすることで、自動的に真ん中にしてくれるというわけです。

あとは、細かいところを完成させていきましょう。

##### navの左側に余白を作ります。

```css:mysite.css
    nav ul{
      margin-left: 210px;
    }
```

![img-css15](https://job555.info/wp-content/uploads/2020/04/img-css15.png)
これで余白が入りました。

##### 自分の画像の写真の余白を整えます。

自分の画像の写真に割り当てられたidは　icon　というidでした。
前回　CSSに　#icon　というものを作りましたので、
それに追加していきます。

下記のCSSを#iconに追加します。

```css:mysite.css
    margin-top: 40px;
    margin-left: 30px;
```

追加したあとは、こんなCSSになりました。

```css:mysite.css
    #icon{
    width: 150px;
    border: solid white;
    border-radius: 10%;
    margin-top: 40px;
    margin-left: 30px;
    }
```

見た目はこんな感じです。

![img-css16](https://job555.info/wp-content/uploads/2020/04/img-css16.png)

##### 自分の名前にも、余白を加えて整えます。

ちょっとアイコン画像と名前がくっつき過ぎていますので、
CSSの#iconに余白を加えます。

下記のCSSを＃iconに追加します。

```css:mysite.css
    margin-right: 20px;
```

    追加したあとは、こんなCSSになりました。

```css:mysite.css
        #icon{
        width: 150px;
        border: solid white;
        border-radius: 10%;
        margin-top: 40px;
        margin-left: 30px;
        margin-right: 20px;
        }
```

見た目はこんな感じです。

![img-css17](https://job555.info/wp-content/uploads/2020/04/img-css17.png

名前の余白を開けるのにも、隣の#iconの右側に
余白をつけることで代用できますし、
CSS的にもわかりやすくていいですね。

##### もう少しスタイリッシュにしてみます。

アイコンをナビゲーションバーに少し重ねてみましょう。
マージンをマイナスに指定すれば、めり込ませることができます。
下記のCSSを＃iconに追加します。

```css:mysite.css
    margin-bottom: -30px;
```

追加したあとは、こんなCSSになりました。

```css:mysite.css
        #icon{
        width: 150px;
        border: solid white;
        border-radius: 10%;
        margin-top: 40px;
        margin-left: 30px;
        margin-right: 20px;
        margin-bottom: -30px;
        }
```

見た目はこんな感じです。

![img-css18](https://job555.info/wp-content/uploads/2020/04/img-css18.png)

このように、画像をめり込ませることができました。
#iconのmarginの下記4つは、１行で書くことができます。

```css:mysite.css
    margin-top: 40px;
    margin-left: 30px;
    margin-right: 20px;
    margin-bottom: -30px;
    }
```

１行で書くときは、top right bottom leftの順で書きます。
###### 上から時計回りと覚えておくといいです。

```css:mysite.css
    margin: 40px 20px -30px 30px;
```

となります。

追加したあとは、こんなCSSになりました。

```css:mysite.css
        #icon{
        width: 150px;
        border: solid white;
        border-radius: 10%;
        margin: 40px 20px -30px 30px;
        }
```

見た目は変わりません。まとめたことによりコードが少なくなり
わかりやすくなりました。


##### ナビゲーションバーの角を丸くしましょう。
アイコンの角を丸くしたように、ナビゲーションバーも角を丸くします。
CSSのnavにborder-radiusを下記のように書いてきます。

```css:mysite.css
    border-radius: 10px 10px 0px 0px;
```

    となります。

追加したあとは、こんなCSSになりました。

```css:mysite.css
    nav{
    background-color: #aacccc;
    border-radius: 10px 10px 0px 0px;
    }
```

見た目はこんな感じです。

![img-css19](https://job555.info/wp-content/uploads/2020/04/img-css19.png)

## コンテンツのデザインをしよう
##### 本文の背景を白くしましょう。
本文の部分はこのようなHTMLになっていました。

```html:mysite.html
    <div class="container">
      <h2>自己紹介</h2>
        <div class="profile">
          <p>愛知県で初の有機JASニンジンを作り、高級スーパーフランテ２４店舗に流通。
          <br>
          年間1200人が受講する「健康セミナー」と有機JASニンジンのコラボ「家族で遊ぶ収穫祭」を10年開催中
          <br>
          副業のアフィリエイトで月収10万円を達成、Webディレクターとして
          個人で営業し、ホームページ制作を受注。
          <hr>
          <p>1986年10月16日生まれ</p>
          <p>愛知県出身</p>
          <p>名古屋経済大学管理栄養学科</p></p>
        </div>
    </div>
```


この本文はdiv class="container"で囲まれていますので、
CSSは .container　に書いていきます。

背景色を白にします。

```css:mysite.css
    .container{
    background-color: white;
    }
```

これで、背景が白くなりました。
フッターの部分を除いて、背景が白くなっていますね。

![img-css20](https://job555.info/wp-content/uploads/2020/04/img-css20.png)

##### 次に、コンテンツ部分をナビゲーションの幅に合わせます。
以前に、headerのdiv class="top"にサイトを中央揃えにしたCSSを
つけたのを覚えているでしょうか。

```css:mysite.css
    .top{
    width: 800px;
    margin: 0px auto 0px auto;
    }
```

このようなCSSを当てましたね。
これと同じように、widthを800px　margin: 0px auto 0px auto;
に指定することで、揃えることができます。
CSSの.container に下記のコードを書きます。

```css:mysite.css
    width: 800px;
    margin: 0px auto 0px auto;
```

これで、navと同じ幅になりました。

追加した後のCSSはこのようになりました。

```css:mysite.css
    .container{
    background-color: white;
    width: 800px;
    margin: 0px auto 0px auto;
    }
```

見た目はこんな感じです。

![img-css21](https://job555.info/wp-content/uploads/2020/04/img-css21.png)

ただ、これでは見栄えが悪いので、内側に余白をつけましょう。

###### 本文の内側に余白をつけていきます。

CSSの.containerに、paddingを追加していきます。
paddingは内側の余白をコントロールするものです。

では、.containerに下記のコードを追加していきましょう。

```css:mysite.css
    padding: 30px 30px 60px 30px;
```

追加したあとは、こんなCSSになりました。

```css:mysite.css
    .container{
    background-color: white;
    width: 800px;
    margin: 0px auto 0px auto;
    padding: 30px 30px 60px 30px;
    }
```

見た目はこんな感じになりました。

![img-css22](https://job555.info/wp-content/uploads/2020/04/img-css22.png)

しかし白い背景の横幅がちょっと出てしまっています。
これを修正しましょう。
このCSSをみてみると、
widthで800px paddingで右30px　左30pxとなっています。

```css:mysite.css
    .container{
    background-color: white;
    width: 800px;
    margin: 0px auto 0px auto;
    padding: 30px 30px 60px 30px;
    }
```

これを修正するには、paddingで左右に30pxずつ、合計
60px出ているので、widthを、-60pxすればいいということになります。
widthを下記のように修正します。

```css:mysite.css
    width 740px;
```

修正したあとは、こんなCSSになりました。

```css:mysite.css
    .container{
    background-color: white;
    width: 740px;
    margin: 0px auto 0px auto;
    padding: 30px 30px 60px 30px;
    }
```

見た目はこんな感じになりました。

![img-css23](https://job555.info/wp-content/uploads/2020/04/img-css23.png)

##### 次に、プロフィールの文章の余白をかっこよくしましょう

プロフィールの文章には、div class="profile"というものがついています。
CSSに、.profileを書いていきましょう。

```css:mysite.css
    .profile{
      padding: 0px 20px 0px 20px;
    }
```

これで、h2タグで書いた「自己紹介」というタイトルと本文に段落ができて
見栄えが良くなりました。

![img-css24](https://job555.info/wp-content/uploads/2020/04/img-css24.png)

##### 次に１行あたりの幅を指定してみやすくします。

CSSの.profileに追記していきます。

```css:mysite.css
    line-height: 35px;
```

追加したあとは、こんなCSSになりました。

```css:mysite.css
    .profile{
      padding: 0px 20px 0px 20px;
      line-height: 35px;
    }
```

見た目はこんな感じになりました。

![img-css25](https://job555.info/wp-content/uploads/2020/04/img-css25.png)
間隔が空いて、かなりみやすくなりましたね。

##### 水平線の上下にも、余白をつけていきましょう。

水平線はhrというタグでした。
CSSにhrを書いていきます。
marginで余白をつけていきましょう。

```css:mysite.css
    hr{
      margin: 20px 0px 20px 0px;
    }
```

さらにみやすくなりました。
![img-css26](https://job555.info/wp-content/uploads/2020/04/img-css26.png)

##### 本文の背景に、角丸をつけていきます。

今までのナビゲーションの時のように、border-radiusをつけていきます。
本文の背景は.containaerでした。
CSSの.containaerに下記を追記していきます。

```css:mysite.css
    border-radius: 0px 0px 10px 10px;
```

追加したあとは、こんなcssになりました。

```css:mysite.css
    .container{
    background-color: white;
    width: 740px;
    margin: 0px auto 0px auto;
    padding: 30px 30px 60px 30px;
    border-radius: 0px 0px 10px 10px;
    }
```

見た目はこんな感じになりました。
![img-css27](https://job555.info/wp-content/uploads/2020/04/img-css27.png)

#### フッターの部分を整えていきましょう。

フッターにはfooterというタグがありました。
CSSの一番下の部分に、footerを追加します。

```css:mysite.css
    footer{

    }
```

場所を固定するためのコードをfooterの中に書きます。
position: fixed;とbottom: 0;を書くことで、一番下に
固定することができます。

```css:mysite.css
    position: fixed;
    bottom: 0;
```

見た目はこんな感じになりました。
![img-css28](https://job555.info/wp-content/uploads/2020/04/img-css28.png)

背景色を変えるため、background-colorを
footerの中に書きます。カラーコードは#9fbb9fとします。

```css:mysite.css
    background-color: #9fbb9f;
```

見た目はこんな感じになりました。

![img-css29](https://job555.info/wp-content/uploads/2020/04/img-css29.png)

文字だけ背景色がついているので、widthで幅を100%にしましょう。
そして、text-align: center;で中央揃えにします。
footerタグの中にさらに書いていきます。

```css:mysite.css
    width: 100%;
    text-align: center;
```

見た目はこんな感じになりました。

![img-css30](https://job555.info/wp-content/uploads/2020/04/img-css30.png)


文字の色を #228822　にし、paddingで
空間を開けましょう。
文字を少し小さくするために、font-sizeで小さくしましょう。
footerタグにさらに書いていきます。

```css:mysite.css
    text-color: #228822;
    padding: 30px 0px;
    font-size: 12px;
```

見た目はこんな感じになりました。

![img-css31](https://job555.info/wp-content/uploads/2020/04/img-css31.png)

これで、ひと通り自己紹介のサイトは完成しました。

![img-css32](https://job555.info/wp-content/uploads/2020/04/img-css32.png)

### ちょっと変更するだけで、自分のサイトに！
これは現在、私の自己紹介サイトになっていますが、

- アイコンの写真
- ヘッダーの写真
- 名前
- ナビゲーションバーのリンク先
- 自己紹介の文章
- フッターの名前

を変更するだけで、簡単にご自身の自己紹介サイトに
変えることができます。

あとは、どんどんポートフォリオをサイトに乗せていくだけで
自己紹介サイト＋ポートフォリオサイトができていきます。
