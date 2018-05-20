# Fake Useragent

各种各样的随机浏览器头 😆


![image](https://api.travis-ci.org/EDDYCJY/fake-useragent.svg?branch=master)

## 安装

```
$ go get github.com/EDDYCJY/fake-useragent
```

## 用法

``` go
package main

import (
	"log"

	"github.com/EDDYCJY/fake-useragent"
)

func main() {
        // 推荐使用
	random := browser.Random()
	log.Printf("Random: %s", random)

	chrome := browser.Chrome()
	log.Printf("Chrome: %s", chrome)

	internetExplorer := browser.InternetExplorer()
	log.Printf("IE: %s", internetExplorer)

	opera := browser.Opera()
	log.Printf("Opera: %s", opera)

	firefox := browser.Firefox()
	log.Printf("Firefox: %s", firefox)

	uc := browser.UC()
	log.Printf("UC: %s", uc)

	safari := browser.Safari()
	log.Printf("Safari: %s", safari)

	android := browser.Android()
	log.Printf("Android: %s", android)

	macOSX := browser.MacOSX()
	log.Printf("MacOSX: %s", macOSX)

	ios := browser.IOS()
	log.Printf("IOS: %s", ios)

	linux := browser.Linux()
	log.Printf("Linux: %s", linux)

	iphone := browser.IPhone()
	log.Printf("IPhone: %s", iphone)

	ipad := browser.IPad()
	log.Printf("IPad: %s", ipad)

}
```

### 定制

你可以调整抓取页面的最大数量、时间间隔以及最大超时时间。 如果不填写，则为默认值。

``` go
client := browser.Client{
	MaxPage: 3,
	Delay: 200 * time.Millisecond,
	Timeout: 10 * time.Second,
}
cache := browser.Cache{}
b := browser.NewBrowser(client, cache)

random := b.Random()
```

更新浏览器头的临时文件缓存

``` go
client := browser.Client{}
cache := browser.Cache{
	UpdateFile: true,
}
b := browser.NewBrowser(client, cache)
```

关闭浏览器头的临时文件缓存（不建议使用）

``` go
client := browser.Client{}
cache := browser.Cache{
	CloseFile: true,
}
b := browser.NewBrowser(client, cache)
```

在最后，我是建议常规用法就好，默认参数能够满足日常需求

### 输出

``` sh
Random: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_13_2) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/63.0.3239.132 Safari/537.36

Chrome: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/60.0.3112.113 Safari/537.36

IE: Mozilla/5.0 (compatible; MSIE 9.0; Windows NT 6.1; WOW64; Trident/5.0)

Opera: Mozilla/5.0 (Windows NT 10.0; WOW64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/52.0.2743.82 Safari/537.36 OPR/39.0.2256.48

Firefox: Mozilla/5.0 (Windows NT 6.3; WOW64; rv:41.0) Gecko/20100101 Firefox/41.0

UC: LG/GT505/v10a Browser/Teleca-Q7.1 MMS/LG-MMS-V1.0/1.2 MediaPlayer/LGPlayer/1.0 Java/ASVM/1.1 Profile/MIDP-2.1 Configuration/CLDC-1.1 UNTRUSTED/1.0 UCWEB/2.0 (Java; U; MIDP-2.0; en-US; lg) U2/1.0.0 UCBrowser/8.9.0.251 U2/1.0.0 Mobile

Safari: Mozilla/5.0 (iPhone; CPU iPhone OS 11_2_5 like Mac OS X) AppleWebKit/604.5.6 (KHTML, like Gecko) Version/11.0 Mobile/15D60 Safari/604.1

Android: Mozilla/5.0 (Linux; Android 6.0; MYA-L22 Build/HUAWEIMYA-L22) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/62.0.3202.84 Mobile Safari/537.36

MacOSX: Mozilla/5.0 (Macintosh; Intel Mac OS X 10_10_5) AppleWebKit/602.2.14 (KHTML, like Gecko) Version/10.0.1 Safari/602.2.14

IOS: Mozilla/5.0 (iPhone; CPU iPhone OS 10_1 like Mac OS X) AppleWebKit/602.2.14 (KHTML, like Gecko) Version/10.0 Mobile/14B72 Safari/602.1

Linux: Mozilla/5.0 (X11; Linux x86_64; rv:42.0) Gecko/20100101 Firefox/42.0

IPhone: Mozilla/5.0 (iPhone; CPU iPhone OS 10_2 like Mac OS X) AppleWebKit/602.3.12 (KHTML, like Gecko) Version/10.0 Mobile/14C92 Safari/602.1

IPad: Mozilla/5.0 (iPad; CPU OS 5_0_1 like Mac OS X) AppleWebKit/534.46 (KHTML, like Gecko) Version/5.1 Mobile/9A405 Safari/7534.48.3
```

## 注意

如果第一次使用，fake-useragent 将收集数据并在临时目录中创建一个文件作为文件缓存，请耐心等待几秒钟

## TODO

- CDN Cache Server


