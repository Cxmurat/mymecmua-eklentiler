# MyMecMua Eklenti Deposu

Bu repo, MyMecMua uygulamasının eklenti güncellemelerini ve uygulama sürüm bilgilerini yönetir.

## Nasıl Çalışır?

Uygulama açıldığında `katalog.json` dosyasını bu repodan çeker ve kurulu eklentilerin sürümlerini karşılaştırır. Güncelleme varsa kullanıcıya onay diyaloğu gösterir.

## Eklenti Güncellemesi Yayınlama

1. Yeni `.myex` dosyasını hazırla
2. GitHub'da yeni bir **Release** oluştur (örn. `eklenti-haberler-v1.1.0`)
3. `.myex` dosyasını Release'e ekle (Assets)
4. `katalog.json` dosyasındaki ilgili eklentinin `surum` ve `indirme_url` alanlarını güncelle
5. Commit & Push

## Uygulama Güncellemesi Yayınlama

1. APK/AAB dosyasını hazırla
2. GitHub'da yeni bir **Release** oluştur (örn. `v1.1.0`)
3. APK dosyasını Release'e ekle
4. `katalog.json` dosyasındaki `uygulama.surum` ve `uygulama.indirme_url` alanlarını güncelle
5. Commit & Push

## katalog.json Formatı

```json
{
  "uygulama": {
    "surum": "1.0.0",
    "notlar": "Güncelleme notları...",
    "indirme_url": "https://github.com/.../releases/download/v1.0.0/mymecmua.apk",
    "zorunlu": false
  },
  "eklentiler": [
    {
      "id": "haberler",
      "ad": "Haberler",
      "surum": "1.0.0",
      "aciklama": "Güncelleme açıklaması",
      "indirme_url": "https://github.com/.../releases/download/.../haberler.myex",
      "zorunlu": false
    }
  ]
}
```

### Alan Açıklamaları

| Alan | Açıklama |
|------|----------|
| `surum` | Semantic versioning (örn. `1.2.3`) |
| `notlar` / `aciklama` | Kullanıcıya gösterilecek güncelleme notu |
| `indirme_url` | Dosyanın doğrudan indirme linki |
| `zorunlu` | `true` ise kullanıcı "Daha Sonra" diyemez |

## Eklenti ID'leri

| ID | Eklenti Adı |
|----|-------------|
| `haberler` | Haberler (RSS Okuyucu) |
