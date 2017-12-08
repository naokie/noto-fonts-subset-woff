# Optimize size

Limit glyph by JIS X 0208.

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
| い | Subset | 939024 byte |
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
| い | Subset | 814304 byte |
| ろ | い & --layout-features='' | 786764 byte |
| は | ろ & --desubroutinize | 750424 byte |


## cf.

### Use woff2_compress

| Set | File | Size | Command |
| --- | --- | --- | --- |
| Raw | NotoSansJP-Regular.otf | 4479576 byte | |
| Subset | NotoSansJP-Regular.subset.otf | 1093092 byte | - `pyftsubset ./src/NotoSansJP-Regular.otf --text-file="./config/chars.jp.min.txt"` |
| Raw woff2 | NotoSansJP-Regular.woff2 | 3310504 byte | - `woff2_compress ./src/NotoSansJP-Regular.otf` |
| Subset woff2 | NotoSansJP-Regular.subset.woff2 | 814304 byte | - `woff2_compress ./src/NotoSansJP-Regular.subset.otf` |
