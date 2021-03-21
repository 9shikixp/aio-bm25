# aio-bm25

## 実行環境
- Python 3.8.3
- Intel Core i5-7500(4コア)
- 24GB (4GBx2, 8GBx2) DDR4-2400
- Ubuntu 18.04

## ライブラリのインストール
poetryが入っている環境で，
```
$ poetry install
```
を実行するか，`pyproject.toml`を参考に，  
pip等で必要なライブラリをインストールしてください．

その後，UniDicの辞書を，
```
$ python -m unidic download
```
でダウンロードしてください．

## 事前準備
`data/`配下に，AI王で配布された`all_entities.json.gz`と`train_questions.json`を置きます．  
`notebooks/build_inverted_index.ipynb`を上のセルから順番に実行すると，  `ir_dumps/`に検索に用いる転置インデックスファイルなどが作成されます．  

## 各ファイルの説明
### notebooks/build_inverted_index.ipynb
検索に用いる転置インデックスファイルなどを作成
### notebooks/search_entity.ipynb
質問文をクエリとした，BM25によるWikipediaの記事検索
### notebooks/sort_sentence.ipynb
質問文をクエリとした，BM25による文の並べ替え
### notebooks/search_entity_candidates.ipynb
質問文と選択肢名をクエリとした，BM25によるWikipediaの記事検索，文の並べ替え

## 補足
- Wikipediaの記事をdict形式で持っているので，RAMが16GBくらいあればスワップ無しで動くと思います．
- ipynbファイルの出力にある実行時間は，上記の実行環境によるものです．AI王のライブコンペで用いた環境とは異なります．

## 参考にしたサイト
- [The first step self made full text search - Speaker Deck](https://speakerdeck.com/ryook/the-first-step-self-made-full-text-search)
- [第7回　転置索引の構築：検索エンジンはいかにして動くのか？｜gihyo.jp … 技術評論社](https://gihyo.jp/dev/serial/01/search-engine)

