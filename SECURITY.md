# Güvenlik Politikası

## Desteklenen sürümler

Güvenlik düzeltmeleri yalnızca en son sürüme yapılır.

## Güvenlik açığı bildirmek

**Lütfen güvenlik açıklarını herkese açık Issues bölümüne yazmayın.**

1. Depo sayfasında **Security › Report a vulnerability** ile gizli bir bildirim gönderin.
2. Bu seçenek görünmüyorsa, ayrıntı vermeden "Güvenlik: iletişim" başlıklı bir issue açın;
   size gizli bir iletişim yolu bildirilir.

Bildirime şunları eklemeniz işi hızlandırır: Unpaxo ve macOS sürümü, sorunu tekrar oluşturan arşiv
ya da adımlar, beklenen ve gerçekleşen davranış. Arşiv açıcılar güvenilmeyen dosyaları işlediği için
özellikle şu türden bulgular önemlidir: hedef klasörün dışına yazma, bellek hataları, sonsuz döngü.

## Unpaxo'nun güvenlik modeli

- **App Sandbox:** İzinler [`Support/Unpaxo.entitlements`](Support/Unpaxo.entitlements) dosyasında;
  **ağ izni yoktur**, yani macOS Unpaxo'nun internete bağlanmasını engeller.
- **Dosya erişimi:** Yalnızca kullanıcının açtığı, sürüklediği ya da seçtiği dosya ve klasörler ile
  İndirilenler klasörü. Onaylanan klasörler güvenli yer imiyle hatırlanır.
- **Yol güvenliği:** Arşivden gelen her yol temizlenir; `..` ya da mutlak yol içeren öğeler çıkarılmaz.
  libarchive tarafında simgesel bağ üzerinden yazma ve `..` reddedilir; RAR tarafında UnRAR'ın kendi
  yol denetimleri geçerlidir. Çıkarma önce gizli bir geçici klasöre yapılır, sonra yerine taşınır.
- **İzinler:** Sahiplik, setuid/setgid ve genişletilmiş öznitelikler arşivden alınmaz.
- **Üçüncü taraf kod:** libarchive, liblzma ve UnRAR resmi kaynak paketlerinden derlenir; paketlerin
  SHA-256 özetleri [`Vendor/build-deps.sh`](Vendor/build-deps.sh) içinde sabitlenmiştir. Bu kütüphanelerde
  yayımlanan güvenlik düzeltmeleri yeni Unpaxo sürümleriyle alınır.
- **Şifreler:** Bellekte tutulur, diske ya da Anahtar Zinciri'ne kaydedilmez.
