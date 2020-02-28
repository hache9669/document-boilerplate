FORMAT: 1A
HOST: http://xxxxx.xx

# テスト用APIドキュメント
[楽天ブックス書籍検索API](https://webservice.rakuten.co.jp/explorer/api/BooksBook/Search/)ライクなサンプルAPI

## Group 書籍情報


### 書籍一覧取得 [GET /api/books/list{?title,author,publisherName,sort}]
リクエストパラメータで書籍を検索した結果を返すAPI

+ Parameters
    + title: `ファイアパンチ` (string, optional) - 書籍タイトル
    + author: `藤本タツキ` (string, optional) - 著者名
    + publisherName: `集英社` (string, optional) - 出版社名
    + sort: `standard` (string, optional) - 並び順[standard or sales or +releaseDate or -releaseDate or +itemPrice or -itemPrice or reviewCount or reviewAverage]

+ Response 200 (application/json)
    + Attributes
        + count: 8 (number, required) - 検索結果件数
        + page: 1 (number, required) - 現在表示中のページインデックス
        + first: 1 (number, required) - 現在表示中の先頭項目インデックス
        + last : 8 (number, required) - 現在表示中の末尾項目インデックス
        + hits: 8 (number, required) - ？？？
        + carrier: 0 (number, required) - ？？？
        + pageCount: 1 (number, required) - 検索結果のページ数
        + Items (array, required) - 
            + (object)
                + Item (object, required)
                    + title: ファイアパンチ 8 (string, required) - タイトル
                    + titleKana: ファイアパンチ  (string, optional) - タイトル(カナ)
                    + subTitle (string, optional) - サブタイトル
                    + subTitleKana  (string, optional) - サブタイトル(カナ)
                    + seriesName: ジャンプコミックス - シリーズ/レーベル名
                    + seriesNameKana (string, optional) - シリーズ/レーベル名(カナ)
                    + contents (string, optional) - ？？？
                    + author: 藤本 タツキ (string, required) - 著者名
                    + authorKana: フジモトタツキ (string, required) - 著者名(カナ)
                    + publisherName: 集英社 (string, required) - 出版社名
                    + size: コミック (string, required) - 版サイズ
                    + isbn: 9784088813271 (string, required) - ISBN
                    + itemCaption (string, optional) - キャプション
                    + salesDate: 2018年02月02日 (string, required) - 発売日
                    + itemPrice: 440 (number, required) - 価格
                    + listPrice: 0 (number, required) -？？？ 
                    + discountRate: 0 (number, required) - 値引き率
                    + discountPrice: 0 (number, required) - 値引き額
                    + itemUrl: https://books.rakuten.co.jp/rb/15262531/ (string, optional) - 商品ページURL
                    + affiliateUrl (string, optional) - アフィリエイトURL
                    + smallImageUrl: https://thumbnail.image.rakuten.co.jp/@0_mall/book/cabinet/3271/9784088813271.jpg?_ex=64x64 (string, optional) - 画像URL(小)
                    + mediumImageUrl: https://thumbnail.image.rakuten.co.jp/@0_mall/book/cabinet/3271/9784088813271.jpg?_ex=120x120 (string, optional) - 画像URL(中)
                    + largeImageUrl: https://thumbnail.image.rakuten.co.jp/@0_mall/book/cabinet/3271/9784088813271.jpg?_ex=200x200 (string, optional) - 画像URL(大)
                    + chirayomiUrl (string, optional) - チラ読みURL
                    + availability: 1 (string, required) - 利用可能フラグ
                    + postageFlag: 0 (number, required) - 送料フラグ
                    + limitedFlag: 0 (number, required) - 限定フラグ
                    + reviewCount: 9 (number, required) - レビュー件数
                    + reviewAverage: 4.25 (string,required) - レビュー平均
                    + booksGenreId: 001001001008 (string, required) - ジャンルID

    + Body
        {{ partial "./json/book_list.md"}}
