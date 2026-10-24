# Industrial Simulation Studio — ürün kütüphanesi

Bu depo, [Industrial Simulation Studio](https://github.com/alizobu92/industrial-simulation-studio-releases)
uygulamasının içinden indirilen **gerçek ürün** tanımlarını yayımlar. Uygulamayla yalnız markasız jenerik
cihazlar gelir; gerçek ürünler ihtiyaç oldukça, **tek tek** indirilir:

*Cihaz kütüphanesi → Gerçek ürün indir… → ürünü seçip İndir.*

Kurulan ürün kütüphanede kendi kategorisinde görünür, internetsiz kullanılır ve uygulama güncellense de kalır.
Kurulu olmayan bir ürünü kullanan proje açılınca uygulama eksik ürünleri indirmeyi önerir.

## İçerik

| Dosya | Açıklama |
|---|---|
| `index.json` | Ürün listesi: kimlik, sürüm, üretici, model, kategori, özet, paket yolu, boyut ve SHA-256 özeti |
| `packages/<kimlik>-<sürüm>.zip` | Ürün paketi: cihaz tanımı (`*.device.json`) ve özgün, stilize görseli |

Uygulama listeyi `https://raw.githubusercontent.com/alizobu92/industrial-simulation-studio-devices/main/index.json`
adresinden okur, paketi indirir, SHA-256 özetini ve tanımın kendisini doğrular; uyuşmayan paket kurulmaz.
Paketler yalnız veri içerir (JSON ve SVG), çalıştırılabilir kod içermez.

Bu depo elle düzenlenmez: tanımlar uygulamanın kaynak deposunda yazılır, aynı doğrulayıcı ve testlerden geçer,
paketleme aracıyla buraya yazılır.

## Kaynaklar ve sorumluluk

- Tanımlar üreticilerin kamuya açık belgelerinden (datasheet, kılavuz, register tablosu, ürün sayfası) derlenir.
  Her bilgi tanımda kaynağına bağlıdır; belgede bulunamayan bilgiler **varsayım** olarak işaretlidir ve
  uygulamada sarı rozetle gösterilir.
- Görseller özgün ve stilizedir; üretici fotoğrafı veya logosu kullanılmaz. Belgelerin kendisi bu depoda
  bulunmaz, tanımlarda adresleriyle anılır.
- Bu depo ve uygulama üreticilerle bağlantılı değildir; ürün adları ve markalar sahiplerine aittir. Simülasyon
  yaklaşık bir modeldir; gerçek kurulumda üreticinin belgeleri esas alınmalıdır.
