# Noto Fonts for Webfont

## Build Noto Sans JP

### Requirements

**Python3**

- [fonttools](https://github.com/fonttools/fonttools)
- [brotli](https://pypi.python.org/pypi/Brotli)
- [zopfli](https://pypi.python.org/pypi/zopfli)

Download "Noto Sans Japanese" from Google Fonts Early Access.
https://fonts.google.com/earlyaccess

### Install

```sh
# Install Python3
$ brew install python3

# Install fonttools
$ pip3 install fonttools

# Install brotli
$ pip3 install brotli

# Install zopfli
$ pip3 install zopfli

# Download Noto Sans Japanese
$ curl -O http://fonts.gstatic.com/ea/notosansjapanese/v6/download.zip
$ unzip ./download.zip -d ./src
```

### Build

Character list

```sh
cat ./config/chars.jp.txt | tr -d '\n' > ./config/chars.jp.min.txt
```

WOFF

```sh
pyftsubset ./src/NotoSansJP-Regular.otf --text-file="./config/chars.jp.min.txt" --flavor=woff --with-zopfli --output-file=./dist/NotoSansJP-Regular.min.woff
pyftsubset ./src/NotoSansJP-Bold.otf --text-file="./config/chars.jp.min.txt" --flavor=woff --with-zopfli --output-file=./dist/NotoSansJP-Bold.min.woff
```

WOFF2

```sh
pyftsubset ./src/NotoSansJP-Regular.otf --text-file="./config/chars.jp.min.txt" --flavor=woff2 --output-file=./dist/NotoSansJP-Regular.min.woff2
pyftsubset ./src/NotoSansJP-Bold.otf --text-file="./config/chars.jp.min.txt" --flavor=woff2 --output-file=./dist/NotoSansJP-Bold.min.woff2
```

### Config

#### chars.jp.txt

http://www.asahi-net.or.jp/~AX2S-KMTN/ref/jisx0208.html を参考に「記号、英数字、かな」「第1水準漢字」のみを含めたテキスト。

#### cf.

- https://ja.wikipedia.org/wiki/Unicode%E4%B8%80%E8%A6%A7_0000-0FFF
- http://www.asahi-net.or.jp/~AX2S-KMTN/ref/jisx0208.html

---

LICENSE

See also [Noto fonts](https://github.com/googlei18n/noto-fonts)
