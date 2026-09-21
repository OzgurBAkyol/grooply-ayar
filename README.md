# grooply-ayar

Grooply uygulamasının açılışta okuduğu tek ayar dosyası.

**Neden var:** sunucu bir Cloudflare hızlı tünelinin arkasında ve o tünelin
adresi her yeniden başlatmada değişiyor. Adres uygulamanın içine gömülseydi
her değişiklikte yeni bir TestFlight derlemesi gerekirdi.

Uygulama açılışta `sunucu.json` dosyasını okuyor, ulaşamazsa içine gömülü
son bilinen adrese düşüyor. Yani bu depo düşse bile uygulama çalışmaya
devam ediyor — yalnız adres güncellenemez.

**Adres değişince:** `sunucu.json` içindeki `sunucu` alanını güncelle ve
commit'le. Uygulama bir sonraki açılışta yeni adresi alır.

Bu depo **herkese açık** olmak zorunda: uygulama kimlik doğrulamadan okuyor.
İçinde sır yok — adres zaten uygulamayı kuran herkesin ulaşabildiği bir şey.
