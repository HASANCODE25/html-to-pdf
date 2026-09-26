# html-to-pdf

Bu proje, tamamen tarayıcı üzerinde (istemci tarafında) çalışan ve hiçbir sunucuya veri göndermeden HTML belgelerini PDF formatına dönüştüren açık kaynaklı bir araçtır. Gizlilik odaklıdır ve verileriniz asla dışarı çıkmaz.

##  Lisans (License)

Bu proje **GNU Affero General Public License v3.0 (AGPL v3)** ile lisanslanmıştır. 
* Bu projenin kodlarını alıp kapalı kaynaklı hale getiremezsiniz.
* Bu aracı bir web sitesi veya bulut hizmeti (SaaS) arkasında kullansanız bile, yaptığınız tüm değişiklikleri ve sistemin ilgili açık kaynak kodlarını kullanıcılarınıza sunmak zorundasınız.

---

##  Çoklu Dil Entegrasyonu (Multi-Language Integration)

Bu dönüştürücü modül, core yapısı JavaScript/Web tabanlı olmasına rağmen **en az 6 farklı programlama dilinde** (Python, C#, Java, Go, PHP, Node.js vb.) iki farklı mimariyle entegre edilerek kullanılabilir:

### 1. Yerel API (Mikro Servis) Mimarisi (Önerilen)
Dönüştürücü yerel bir port üzerinden (örneğin `localhost:3000`) hafif bir HTTP sunucusu gibi çalıştırılır. Kullanmak istediğiniz dil üzerinden standart bir HTTP POST isteği göndererek dönüştürme işlemini yapabilirsiniz.

**Örnek Python İsteği:**
```python
import requests

url = "http://localhost:3000/convert"
html_data = "<h1>Merhaba Dünya</h1>"
response = requests.post(url, json={"html": html_data})

with open("cikti.pdf", "wb") as f:
    f.write(response.content)
```

### 2. CLI (Komut Satırı Arabirimi) Mimarisi
Proje bir terminal komutuna dönüştürülür. Kullandığınız programlama dilinin sistem komutu çalıştırma fonksiyonlarını kullanarak tetikleyebilirsiniz.

**Örnek C# / .NET İsteği:**
```csharp
using System.Diagnostics;

Process startInfo = new Process();
startInfo.StartInfo.FileName = "html-pdf-converter";
startInfo.StartInfo.Arguments = "--input dosya.html --output cikti.pdf";
startInfo.Start();
```

---

##  Özellikler

- **%100 İstemci Tarafı:** Sunucu maliyeti yoktur, dönüşüm doğrudan kullanıcının cihazında gerçekleşir.
- **Esnek Sayfa Ayarları:** A4, Letter, Legal boyutları ile Yatay/Dikey yönlendirme desteği.
- **Kenar Boşluğu Yönetimi:** Geniş, normal veya sıfır kenar boşluğu seçenekleri.
- **Gelişmiş CSS Desteği:** `@media print` kuralları ile tam uyumluluk.

##  Kurulum ve Çalıştırma

Projenin tarayıcı arayüzünü yerelde çalıştırmak için adımları takip edin:

1. Depoyu bilgisayarınıza kopyalayın:
   ```bash
   git clone https://github.com/HASANCODE25/html-to-pdf/
   ```
2. Proje dizinine gidin:
   ```bash
   cd html to pdf
   ```
3. `index.html` dosyasını tarayıcınızda açarak hemen kullanmaya başlayın.
