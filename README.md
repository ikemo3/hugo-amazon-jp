# hugo-amazon-jp

[Hugo][]で、Amazon(JP)のアフィリエイトリンクを作るためのテーマコンポーネントです。

[Hugo]: https://gohugo.io/

## 前提条件

[Theme Components][]を使用するため、[Hugo][] 0.42以上が必要です。

## テンプレートへの組み込み方法

### アソシエイトIDの設定

config.tomlに以下のような記述を追加してください。

```toml
[params]
amazonJpAffiliate = "アソシエイトID"
```

ショートコードとして使用します。

### 書籍データの作成

[Data Templates][]を使います。

* カテゴリ: ファイル名を指定するキー
* キー: 書籍など、Amazonの商品を指定するためのキー

ファイル名を `data/カテゴリ.yaml` として、以下のようなファイルを追加します。
以下の例の場合、「プロフェッショナルの条件」があとで使う「キー」になります。

```
"プロフェッショナルの条件":
  asin: 4478300593
  title: プロフェッショナルの条件――いかに成果をあげ、成長するか (はじめて読む>ドラッカー (自己実現編))
```

### リンクの追加

Markdown中に、以下のようなショートコードを埋め込んでください。

画像ありリンク

```
{{< amazon category="カテゴリ" key="キー" >}}
```

リンクのみ(画像なし)の場合

```
{{< amazon-link category="カテゴリ" key="キー" >}}
```

## ライセンス

MITライセンスです。

[Data Templates]: https://gohugo.io/templates/data-templates/
[Hugo]: https://gohugo.io/
[Theme Components]: https://gohugo.io/themes/theme-components/
