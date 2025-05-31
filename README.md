# bbsmenu

板メニュー（bbsmenu）を解析・管理するためのリポジトリです。

## ファイル

- 5ch.net 関係
  - `data/5ch.net/bbsmenu.json` - 板メニューのJSON表現
  - `data/5ch.net/bbsmenu.html` - 板メニューの生のHTML表現（オリジナルエンコーディング）
  - `data/5ch.net/bbsmenu.utf-8.html` - 板メニューの生のHTML表現（UTF-8 エンコーディング）
  - `data/5ch.net/bbsmenu.utf-8-bom.html` - 板メニューの生のHTML表現（UTF-8 with BOM エンコーディング）

## 5ch.net BBS menu の更新

[5ch BBS menu](https://menu.5ch.net/) から下記の手順で html と json の両方を更新します。

### bbsmenu.json の更新方法

1. 5ch BBS menu から [bbsmenu.json](https://menu.5ch.net/bbsmenu.json) のリンクをブラウザで開きます。
2. 表示された JSON データをコピーして、本リポジトリ内の data/5ch.net/bbsmenu.json として UTF-8 で保存します。
3. ワンラインになっている JSON を整形します。（git で差分を管理しやすくするためです。）

### bbsmenu.html の更新方法

1. 5ch BBS menu から [bbsmenu.html](https://menu.5ch.net/bbsmenu.html) のリンクをブラウザで開きます。
2. ページ内で右クリックして "ページのソースを表示" メニューを選択します。（Google Chrome の場合）
3. 表示された内容をコピーして、本リポジトリ内の data/5ch.net/bbsmenu.html として **エンコーディングを変えずに保存** します。

#### 注意点

- テキストは整形しないでください。ただし、
  - ドキュメント冒頭および末尾の空行は除去します。
  - 各行末尾の空白は除去します。

### bbsmenu.utf-8.html の更新方法

1. 5ch BBS menu から [bbsmenu.html](https://menu.5ch.net/bbsmenu.html) のリンクをブラウザで開きます。
2. ページ内で右クリックして "ページのソースを表示" メニューを選択します。（Google Chrome の場合）
3. 表示された内容をコピーして、本リポジトリ内の data/5ch.net/bbsmenu.utf-8.html として **UTF-8 エンコーディングで保存** します。
4. HTML 中の文字コード指定を UTF-8 に修正します。（下記参照）

#### HTML 文字コード指定の変更手順

HTMLのMETAタグ内の文字コード宣言を次のように書き換えます。

変更前
```
<META http-equiv="Content-Type" content="text/html; charset=Shift_JIS">
```

変更後
```
<META http-equiv="Content-Type" content="text/html; charset=utf-8">
```

#### 注意点

- テキストは整形しないでください。ただし、
  - ドキュメント冒頭および末尾の空行は除去します。
  - 各行末尾の空白は除去します。

### bbsmenu.utf-8-bom.html の更新方法

文字エンコーディングを UTF-8-BOM で行う他は、bbsmenu.utf-8.html と同様の手順に従います。
META タグの charset 指定も "utf-8" です。
