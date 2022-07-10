# tidy-radio-files  
OLYMPUS Radio Server Pocket PJ-35 のファイルを整理するためのスクリプト

# How to use

## File tree

<pre>
radio
├── scripts
│   ├── tidy.py
│   └── program.json
├── programs
│   ├── category-a
│   │   └── program-a
│   │       └── YYYYMM
│   │           └── mp3files...
│   └── category-b
│       └── program-b
│           └── YYYYMM
│               └── mp3files...
└── tmp
</pre>

## program.json

json形式で録音した番組の情報を作っておく

```{json}
{
    "[week number]":{
        "[hour minutes]":{"name":"program-a", "category":"category-a"}
    }...
}
```

例えばこんな感じ

```{json}
{
    "0":{
        "0645":{"name":"NHKラジオ英会話", "category":"english"},
        "0830":{"name":"英会話タイムトライアル", "category":"english"},
        "0910":{"name":"エンジョイ・シンプル・イングリッシュ", "category":"english"},
        "0915":{"name":"ラジオビジネス英語", "category":"english"},
        "0930":{"name":"ニュースで学ぶ現代英語", "category":"english"}
    },
    "1":{
        "0645":{"name":"NHKラジオ英会話", "category":"english"},
        "0830":{"name":"英会話タイムトライアル", "category":"english"},
        "0915":{"name":"ラジオビジネス英語", "category":"english"},
        "0910":{"name":"エンジョイ・シンプル・イングリッシュ", "category":"english"},
        "0930":{"name":"ニュースで学ぶ現代英語", "category":"english"},
        "0100":{"name":"深夜の馬鹿力" ,"category":"comedian"}
    }
}
```

## Execution

1. ラジオサーバーからファイルを`tmp`にコピーする
2. `tidy.py`を実行する

```{shell}
$ cd [radio directory]
$ python scripts/tidy.py
```

