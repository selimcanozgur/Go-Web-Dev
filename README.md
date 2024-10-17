# 🔵 Go Hakkında

Go, basit, hızlı ve günvenilir yazılımlar oluşturmak için tasarlanmış açık kaynaklı bir programlama dilidir.

## 📘 Bölüm 1 Giriş

Go, dahili özelliklere sahip bir programlama dilidir ve içerisinde yerleşik bir web sunucsu bulunur.
net/httpStandart kütüphaneden gelen paket, HTTP protokolüyle ilgili tüm işlevleri içerir.

### Bir İstek İşleyicisi Kaydetme

Fonksiyon iki parametre alır:

http.ResponseWriterMetin/html cevabınızı yazacağınız yer burasıdır .
http.RequestBu HTTP isteği hakkında URL veya başlık alanları gibi tüm bilgileri içeren bir .

Bir istek işleyicisini varsayılan HTTP Sunucusuna kaydetmek şu kadar basittir:

```go
package main

import (
    "fmt"
    "net/http"
)

func main() {
    http.HandleFunc("/", func (w http.ResponseWriter, r *http.Request) {
        fmt.Fprintf(w, "Hello, you've requested: %s\n", r.URL.Path)
    })

    http.ListenAndServe(":8080", nil)
}
```
