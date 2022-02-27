# CGST_clock
配信者向けのデレステUI風時計です。  
OBSなどの配信ソフトに取り込んで、現在時刻を配信画面にのせる用途を想定しています。  
ガシャ画面右下などにあるボタンをかなり参考に、画像を使わず作成しました。  
![](/readme_img/button.png)   
こんな感じの表示です (クリックで実際に動いてるページが開きます(逆に動いてる時計をクリックするとここのページが開きます)) 。  
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
※幅と高さはデフォルトのサイズでも構いませんが、418x239だとほぼピッタリになるので、画面内に配置する際に使い勝手が良くなります (フォントをカスタマイズしたりしない限り)。  
※表示されていないときに～のオプションは、別のシーンに切り替えていて表示していないときなど、メモリなどの使用が節約できて若干恩恵を受けるかもしれません。  
米どうせ1秒に1回更新すれば十分なので、「☑カスタムフレームレートを使用」でFPSの値を1とかにするとちょっと軽くなるかもしれません。

- OBSのプレビューに出てきます。  
![](/readme_img/preview.png)  
  
## 日付、曜日、秒や背景のいろいろを消したい場合(OBSの使い方)  
- 上記で追加したソースのプロパティを開き、『カスタムCSS』に以下を **追記** します。  
　  
```
/* 日付、曜日が消えます */
#datenday { display: none; }

/* 秒の棒が消えます + バランスが若干悪くなるのを調整します*/
#sec { display: none; }
#time { margin-bottom: -20px; } /* -20の数字を変えると時刻の下側の余白の高さが変わります */

/* 背景の★が消えます */
.star { display: none; }

/* 背景のボタンっぽい光沢が消えます */
#gloss { background: #FEFEFE; }

```  

日付、曜日の列を消すとこんな感じです。  
![](/readme_img/clock_nodate.png)  
  
日付、曜日、秒を消すとこんな感じです。  
![](/readme_img/clock_nodatesec.png)  

全部追記した場合の『カスタムCSS』欄はこんな感じです。  
**最初から入力されている `body～` はそのままで**、次の行以降に追記してください。  
![](/readme_img/customcss.png)


## ローカルで使う場合
[ここ](https://github.com/uzuky/CGST_clock) にある `clock.css` と `clock.html` をダウンロードして同じディレクトリに入れ、OBSの場合はURLを指定する代わりに「☑ローカルファイル」で `clock.html` を指定して使用してください。  
ローカルで使う **メリットはGitHubが落ちても大丈夫** なところと、 **もっと柔軟にレイアウトをいじれる** ところです。  
たとえば、**秒の棒の色や曜日の色は clock.html 内に直打ちされた JS で指定されているため、色を変えるにはダウンロードしてファイルを編集する必要があります**。  
秒の棒の色は90行目、曜日の色は112行目から118行目のところです。  

# フォントについて
今回用いているのは『GoogleFonts』で公開されている『[Roboto](https://fonts.google.com/specimen/Roboto)』です。  
一方、デレステのUIで使われているフォントは『[ロダンNTLG Pro](https://lets.fontworks.co.jp/fonts/236)』です。  


## 『Fontworks LETS』を契約していて『ロダンNTLG Pro』が使える場合  
(OBSの設定例) ソース一覧からこの時計のプロパティを開き、以下を設定すると、かなりデレステに近づきます。  
幅: `548`  
高さ: `265`   
『カスタムCSS』に以下を追記
```
.dateall {
    font-family: 'FOT-ロダンNTLG Pro';
    font-weight: 600;
    width: 540px;
}
#time {
    margin: -70px 0 -60px;
}
.datenday {
    margin: -15px 0 -20px;
}
```


## 『ニタラゴ』について  
実は『[ロダンNTLG](https://fontworks.co.jp/fontsearch/RodinNTLGPro-EB/)』は『ニタラゴ』から派生したフォントという歴史があります。  
そして『ニタラゴ』は現在『[ニタラゴルイカ](https://www.type-labo.jp/Hanpunitalago.html)』として比較的安く販売されており、デレステフォント界隈では有名なフォントですが、 **英数字部分に関しては『ロダンNTLG』と一致していません**。  
そのため、 **英数字しか使わない時計に『ニタラゴルイカ』を適用してもデレステとは100%違うフォントになります**。(全体的に重心の高さが異なっている他、特に1が決定的に違う)  
![](/readme_img/rodinntlgpro.png)  
↑ 『ロダンNTLG』  
![](/readme_img/nitalagoruika.png)  
↑ 『ニタラゴルイカ』  

# 作者の使用例  
[https://twitch.tv/uzuky](https://twitch.tv/uzuky) を適当に見て  
(自分用のはフォントをいじったりしています)  

# お問い合わせ  
[https://mstdn.maud.io/@uzuky](https://mstdn.maud.io/@uzuky)  

# ライセンス  
MIT
