# Optimize size

## Build .woff by NotoSansJP-Regular.otf

### Optimize setting

| ID | Options command |
| --- | --- |
| ろ | `pyftsubset ./src/NotoSansJP-Regular.otf --text-file="./config/chars.jp.min.txt" --flavor=woff --output-file=./dist/NotoSansJP-Regular.min.woff` |
| は | `pyftsubset ./src/NotoSansJP-Regular.otf --text-file="./config/chars.jp.min.txt" --flavor=woff --with-zopfli --output-file=./dist/NotoSansJP-Regular.min.woff` |
| に | `pyftsubset ./src/NotoSansJP-Regular.otf --text-file="./config/chars.jp.min.txt" --flavor=woff --with-zopfli --output-file=./dist/NotoSansJP-Regular.min.woff --layout-features=''` |
| ほ | `pyftsubset ./src/NotoSansJP-Regular.otf --text-file="./config/chars.jp.min.txt" --flavor=woff --with-zopfli --output-file=./dist/NotoSansJP-Regular.min.woff --layout-features='' --desubroutinize` |

### Result

| ID | Options | Size |
| -- | --- | --- |
| い | Raw file | 4479576 byte |
| ろ | Limit glyph by JIS X 0208 | 939024 byte |
| は | い & --with-zopfli | 924048 byte |
| に | は & --layout-features='' | 890432 byte |
| ほ | に & --desubroutinize | 884008 byte |
