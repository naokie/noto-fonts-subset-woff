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

#### cf.

- https://ja.wikipedia.org/wiki/Unicode%E4%B8%80%E8%A6%A7_0000-0FFF
- http://www.asahi-net.or.jp/~AX2S-KMTN/ref/jisx0208.html
