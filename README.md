# CGST_clock
デレステUI風時計です。  
秒表示は2進数のバーになっています。  
[こんな感じの表示です。](https://uzuky.github.io/CGST_clock/clock.html)

## OBSでの使い方  
- ソース追加で『ブラウザ』を選びます。  
![](/readme_img/source.png)  

- 既定値から以下の部分を設定します。  
URL: `https://uzuky.github.io/CGST_clock/clock.html`  
幅: `418`  
高さ: `238`  
☑表示されていないときにソースをシャットダウン  
![](/readme_img/setting.png)  
※幅と高さはデフォルトのサイズでも構いませんが、418x238だとピッタリになるので、画面内に配置する際に使い勝手が良くなります。  
※表示されていないときに～のオプションは、別のシーンに切り替えていて表示していないときなど、メモリなどの使用が節約できて若干恩恵を受けるかもしれません。  

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


# 使用例  
[https://twitch.tv/uzuky](https://twitch.tv/uzuky) を適当に見て  
(自分用のはフォントをいじったりしています)  


# ライセンス  
MIT