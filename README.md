# make-ti-spoile
指定されたチャンネルに投稿された画像ファイルにスポイラーをかけるだけのbot

## 環境
- Python 3.9.8 or higher
- discord.py 2.3.2 or higher

# 利用方法

## ライブラリのインストール
```bash
python -m pip install -r requirements.txt
```

## 定数の定義
config_sample.jsonをconfig.jsonにリネームして複製する。  
いい感じに編集する。

BotTokenはString、channelIDはIntなので、気を付けて。
```json
{
    "DISCORD_BOT_TOKEN": "DISCORD_BOT_TOKEN",
    "CHANNEL": [
        12345,
        12345
    ],
    "LOG_ROOM_CHANNEL": 12345
}
```

## 実行
```bash
python main.py
```

systemdのserviceとして登録したい場合は、以下のgistを参考にしてください。  
[pythonプログラムをserviceとして登録する時のテンプレ](https://gist.github.com/hyouhyan/392ec36b5588ca5d8376ff7ab3529085)


## Dockerfile
```
docker build -t make-it-spoiler .
docker run -d --restart always --name make-it-spoiler make-it-spoiler
```
