# Değişiklik Günlüğü

Unpaxo'daki tüm önemli değişiklikler bu dosyada, en yeni sürüm en üstte olacak şekilde listelenir.
Biçim [Keep a Changelog](https://keepachangelog.com/tr-TR/1.1.0/) düzenine, sürüm numaraları
[Anlamsal Sürümleme](https://semver.org/lang/tr/) kurallarına dayanır.

## [Yayınlanmamış]

## [1.0] - yayımlanmadı

İlk sürüm.

### Eklenenler
- **Arşiv açma:** ZIP, RAR (RAR4, RAR5, çok parçalı), 7Z, TAR, TAR.GZ, TAR.BZ2, TAR.XZ ve tek dosyalık GZ, BZ2, XZ.
- **İçeriğe göz atma:** klasör ağacı, boyut ve tarih; tümünü ya da yalnızca seçilenleri çıkarma.
- **Şifreli arşivler:** şifreli ZIP ve RAR açma.
- **Arşiv oluşturma:** ZIP (isteğe bağlı AES-256 şifre), 7Z, TAR, TAR.GZ, TAR.BZ2, TAR.XZ.
- **Toplu çıkarma:** birden çok arşiv birlikte bırakılınca sırayla çıkarılır.
- **Güvenli çıkarma:** üzerine yazmama ("Ad 2"), hedef klasör dışına taşan yolların atılması, iptalde yarım dosya bırakmama, boş disk alanı denetimi.
- **Finder ile çalışma:** çift tıklama ve "Birlikte Aç"; sürükle-bırak.
- **Dil:** Türkçe ve İngilizce; Ayarlar'dan değiştirilebilir.
- **Gizlilik:** App Sandbox, ağ izni yok.

### Bilinen sınırlar
- Şifreli 7Z arşivleri açılamıyor.
- Çok parçalı RAR, parçaların bulunduğu klasöre erişim varsa açılır (İndirilenler'de doğrudan, başka klasörlerde bir kez onayla).
