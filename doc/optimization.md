# Optimize size

## Build .woff by NotoSansJP-Regular.otf

### Optimize setting

| ID | Options command |
| --- | --- |
| い | `pyftsubset ./src/NotoSansJP-Regular.otf --text-file="./config/chars.jp.min.txt" --flavor=woff --output-file=./dist/NotoSansJP-Regular.min.woff` |
| ろ | `pyftsubset ./src/NotoSansJP-Regular.otf --text-file="./config/chars.jp.min.txt" --flavor=woff --with-zopfli --output-file=./dist/NotoSansJP-Regular.min.woff` |
| は | `pyftsubset ./src/NotoSansJP-Regular.otf --text-file="./config/chars.jp.min.txt" --flavor=woff --with-zopfli --output-file=./dist/NotoSansJP-Regular.min.woff --layout-features=''` |
| に | `pyftsubset ./src/NotoSansJP-Regular.otf --text-file="./config/chars.jp.min.txt" --flavor=woff --with-zopfli --output-file=./dist/NotoSansJP-Regular.min.woff --layout-features='' --desubroutinize` |

### Result

| ID | Options | Size |
| -- | --- | --- |
| い | Limit glyph by JIS X 0208 | 939024 byte |
| ろ | い & --with-zopfli | 924048 byte |
| は | は & --layout-features='' | 890432 byte |
| に | に & --desubroutinize | 884008 byte |


## Build .woff2 by NotoSansJP-Regular.otf

### Optimize setting

| ID | Options command |
| --- | --- |
| い | `pyftsubset ./src/NotoSansJP-Regular.otf --text-file="./config/chars.jp.min.txt" --flavor=woff2 --output-file=./dist/NotoSansJP-Regular.min.woff2` |
| ろ | `pyftsubset ./src/NotoSansJP-Regular.otf --text-file="./config/chars.jp.min.txt" --flavor=woff2 --output-file=./dist/NotoSansJP-Regular.min.woff2 --layout-features=''` |
| は | `pyftsubset ./src/NotoSansJP-Regular.otf --text-file="./config/chars.jp.min.txt" --flavor=woff2 --output-file=./dist/NotoSansJP-Regular.min.woff2 --layout-features='' --desubroutinize` |

### Result

| ID | Options | Size |
| -- | --- | --- |
| い | Limit glyph by JIS X 0208 | 814304 byte |
| ろ | い & --layout-features='' | 786764 byte |
| は | ろ & --desubroutinize | 750424 byte |
