# CGST_clock
配信者向けのデレステUI風時計です。  
OBSなどの配信ソフトに取り込んで、現在時刻を配信画面にのせる用途を想定しています。  
ガシャ画面右下などにあるボタンをかなり参考に、画像を使わず作成しました。  
![](/readme_img/button.png)   
こんな感じの表示です (クリックで動いてるページが開きます) 。  
[![](/readme_img/clock.png)](https://uzuky.github.io/CGST_clock/clock.html)  
秒表示は2進数のバーになっています。  

## OBSでの使い方  
- ソース追加で『ブラウザ』を選びます。  
![](/readme_img/source.png)  

- 既定値から以下の部分を設定します。  
URL: `https://uzuky.github.io/CGST_clock/clock.html`  
幅: `418`  
高さ: `239`  
☑表示されていないときにソースをシャットダウン  
![](/readme_img/setting.png)  
※幅と高さはデフォルトのサイズでも構いませんが、418x239だとほぼピッタリになるので、画面内に配置する際に使い勝手が良くなります。  
※表示されていないときに～のオプションは、別のシーンに切り替えていて表示していないときなど、メモリなどの使用が節約できて若干恩恵を受けるかもしれません。  
米どうせ1秒に1回更新すれば十分なので、「カスタムフレームレートを使用」にチェックしてFPSの値を1とかにするとちょっと軽くなるかもしれません。

- OBSのプレビューに出てきます。  
![](/readme_img/preview.png)  
  
## 日付、曜日を消したい場合(OBSの使い方)  
- 上記で追加したソースのプロパティを開き、『カスタムCSS』に以下を追記します。  
```  
.datenday { display: none; }  
```  
- OKを押すと日付、曜日の列が消えます。  
![](/readme_img/clock_nodate.png)  

## 秒も消したい場合(OBSの使い方)
- 上記で追加したソースのプロパティを開き、『カスタムCSS』に以下を追記します。  
```
#sec { display: none; }
#time { margin-bottom: -20px; }
```
- OKを押すと秒のバーが消えます。  
日付、曜日、秒を消すとこんな感じです。  
![](/readme_img/clock_nodatesec.png)  

両方追記した場合の『カスタムCSS』欄はこんな感じです。  
最初から入力されている `body～` はそのまま、次の行に追記してください。  
![](/readme_img/customcss.png)

## 背景の★を消したい場合(OBSの使い方)  
- 上記と同様に、以下を追記します。
```
.star { display: none; }
```

## ローカルで使う場合
[ここ](https://github.com/uzuky/CGST_clock) にある `clock.css` と `clock.html` をダウンロードして同じディレクトリに入れ、OBSの場合はURLを指定する代わりにローカルファイルで `clock.html` を指定して使用してください。  
ローカルで使うメリットはGitHubが落ちても大丈夫なところです。  

# フォントについて
今回用いているのはGoogleFontsで公開されている[Roboto](https://fonts.google.com/specimen/Roboto)です。  
デレステのUIで使われているフォントはロダンNTLGなので、Fontworks LETSを契約していて使える方は以下を入力すると、よりデレステのUIに近づくかもしれません。  
```
.dateall { font-family: 'ロダンNTLG EB'; }
```
(ただし、レイアウトが崩れる可能性が高いので、おそらく `.dateall{margin:410px;}` 、 `#time{margin: -20px 0 -10px;}` の値を調整する必要があると思います。あと、フォントを持っていないため **'ロダンNTLG EB'が正しい指定名なのか不明** なので気をつけて下さい。)

## ニタラゴについて  
実は[ロダンNTLG](https://fontworks.co.jp/fontsearch/RodinNTLGPro-EB/)はニタラゴから派生したフォントという歴史があります。  
そしてニタラゴは現在[ニタラゴルイカ](https://www.type-labo.jp/Hanpunitalago.html)として比較的安く販売されており、デレステフォント界隈では有名なフォントですが、 **英数字部分に関しては一致していない** ので使ってもあまりそれっぽくならないかもしれません。(全体的に重心の高さが異なっている他、特に1が決定的に違う)  
![](/readme_img/rodinntlgpro.png)  
↑ ロダンNTLG  
![](/readme_img/nitalagoruika.png)  
↑ ニタラゴルイカ  

# 作者の使用例  
[https://twitch.tv/uzuky](https://twitch.tv/uzuky) を適当に見て  
(自分用のはフォントをいじったりしています)  

# お問い合わせ  
[https://mstdn.maud.io/@uzuky](https://mstdn.maud.io/@uzuky)  

# ライセンス  
MIT
