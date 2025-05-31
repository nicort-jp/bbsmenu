# bbsmenu

板メニュー（bbsmenu）を解析・管理するためのリポジトリです。

## ファイル

- 5ch.net 関係
  - `data/5ch.net/bbsmenu.html` - 5ch.net板メニューの生のHTML表現
  - `data/5ch.net/bbsmenu.json` - 同じデータの構造化されたJSON表現

## 5ch.net bbsmenu の更新

[5ch BBS menu](https://menu.5ch.net/) から下記の手順で html と json の両方を更新します。

### bbsmenu.html の更新方法

1. 5ch BBS menu から [bbsmenu.html](https://menu.5ch.net/bbsmenu.html) のリンクをブラウザで開きます。
2. ページ内で右クリックして "ページのソースを表示" メニューを選択します。（Google Chrome の場合）
3. 表示された内容をコピーして、本リポジトリ内の data/5ch.net/bbsmenu.html として **UTF-8 で保存** します。
4. 文字コードの記載を Shift-JIS から UTF-8 に修正します。（下記参照）

#### 文字コード変更手順

HTMLのMETAタグ内の文字コード宣言を次のように書き換えます。

変更前
```
<META http-equiv="Content-Type" content="text/html; charset=Shift_JIS">
```

変更後
```
<META http-equiv="Content-Type" content="text/html; charset=utf-8">
```

#### その他の注意点

- テキストは整形しないでください。ただし、
  - ドキュメント冒頭および末尾の空行は除去します。
  - 各行末尾の空白は除去します。

### bbsmenu.json の更新方法

1. 5ch BBS menu から [bbsmenu.json](https://menu.5ch.net/bbsmenu.json) のリンクをブラウザで開きます。
2. 表示された JSON データをコピーして、本リポジトリ内の data/5ch.net/bbsmenu.json として UTF-8 で保存します。
3. ワンラインになっている JSON を整形します。（git で差分を管理しやすくするためです。）
