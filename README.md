# YouTube-Chat-Highlight-Extractor

このリポジトリには、YouTubeライブ配信からチャットデータを抽出および分析するためのツールが含まれています。このツールは、チャット内で最も頻繁に使用される単語を特定し、それらの単語の出現頻度を時間ごとに示すグラフを生成します。また、出現頻度に単一のピークがある単語を特定し、これらの単語を使用して配信の重要な瞬間をハイライトします。

## 概要

このシステムは以下のステップを実行します：
1. 指定されたYouTubeライブ配信からチャットデータをダウンロードします。
2. コメントを分析して最も頻繁に使用される単語を特定します。
3. 単語の出現頻度の時間シリーズグラフを生成します。
4. 出現頻度に単一のピークがある単語を特定し、これらの単語をハイライトします。

## 必要条件

- Python 3.7+
- `chat_downloader`
- `google-api-python-client`
- `pandas`
- `matplotlib`
- `tqdm`
- `mecab-python3`
- `uuid`

## インストール

1. リポジトリをクローンします：
    ```sh
    git clone https://github.com/your-username/YouTube-Chat-Highlight-Extractor.git
    cd YouTube-Chat-Highlight-Extractor
    ```

2. 仮想環境を作成します：
    ```sh
    python -m venv venv
    source venv/bin/activate  # Windowsでは `venv\Scripts\activate` を使用
    ```

3. 必要なパッケージをインストールします：
    ```sh
    pip install -r requirements.txt
    ```

4. MeCabとその辞書をセットアップします：
    - お使いのOSに応じた手順に従って、MeCabとIPA辞書をインストールします。

5. `config.py`ファイルを作成し、YouTube APIキーを追加します：
    ```python
    # config.py
    API_KEY = 'YOUR_VALID_API_KEY'
    ```

## 使用方法

ツールを実行するには、以下のコマンドを使用します：
```sh
python main.py <YouTube URL>
```

## 実行例

```sh
$ python main.py https://www.youtube.com/live/lRwUNHq7WVY
Downloading chat data: 100%|█████████████████████████████████████████| 1000/1000 [00:10<00:00, 100.00message/s]
Most common words (Top 20):
1. コメント: 123
2. 配信: 98
3. 楽しい: 76
4. ありがとう: 65
5. いいね: 54
6. 見てる: 45
7. チャンネル: 40
8. ファン: 39
9. 質問: 37
10. 最高: 36
11. 面白い: 35
12. すごい: 34
13. 最高: 33
14. 応援: 32
15. 音楽: 31
16. 動画: 30
17. お願い: 29
18. 頑張って: 28
19. 素晴らしい: 27
20. 綺麗: 26
Selected word for plotting: 楽しい
'楽しい' has a single peak at minute 43
```

## ディレクトリ構造

生成されたグラフは以下のディレクトリ構造で保存されます：
```
graphs/
    <video_id>/
        <YYYYMMDD>/
            <run_id>/
                <rank>_<word>_frequency.png
                <rank>_<selected_word>_frequency_selected.png
```

## ライセンス

このプロジェクトはMITライセンスの下でライセンスされています。
```

## `requirements.txt`

以下の内容で`requirements.txt`を作成します：

```txt
chat_downloader
google-api-python-client
pandas
matplotlib
tqdm
mecab-python3
uuid
```
