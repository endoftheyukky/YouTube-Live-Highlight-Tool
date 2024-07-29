# YouTube-Chat-Highlight-Extractor

This repository contains a tool for extracting and analyzing chat data from YouTube live streams. The tool identifies the most frequently used words in the chat and generates graphs showing the frequency of these words over time. It also identifies words with a single peak in frequency, which can be used to highlight key moments in the stream.

## Overview

The system performs the following steps:
1. Downloads chat data from a specified YouTube live stream.
2. Analyzes the comments to identify the most frequently used words.
3. Generates time series graphs of the word frequencies.
4. Identifies words with a single peak in their frequency and highlights these words.

## Requirements

- Python 3.7+
- `chat_downloader`
- `google-api-python-client`
- `pandas`
- `matplotlib`
- `tqdm`
- `mecab-python3`
- `uuid`

## Installation

1. Clone the repository:
    ```sh
    git clone https://github.com/your-username/YouTube-Chat-Highlight-Extractor.git
    cd YouTube-Chat-Highlight-Extractor
    ```

2. Create a virtual environment:
    ```sh
    python -m venv venv
    source venv/bin/activate  # On Windows use `venv\Scripts\activate`
    ```

3. Install the required packages:
    ```sh
    pip install -r requirements.txt
    ```

4. Set up MeCab and its dictionary:
    - Follow the instructions for your operating system to install MeCab and the IPA dictionary.

5. Create a `config.py` file and add your YouTube API key:
    ```python
    # config.py
    API_KEY = 'YOUR_VALID_API_KEY'
    ```

## Usage

To run the tool, use the following command:
```sh
python main.py <YouTube URL>
```

## Example

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

## Directory Structure

The generated graphs will be saved in the following directory structure:
```
graphs/
    <video_id>/
        <YYYYMMDD>/
            <run_id>/
                <rank>_<word>_frequency.png
                <rank>_<selected_word>_frequency_selected.png
```

## License

This project is licensed under the MIT License.
```
