# Firebase Kurulum Rehberi

## Adım 1: Firebase Projesi Oluşturma

1. https://console.firebase.google.com/ adresine gidin
2. "Proje Ekle" (Add Project) butonuna tıklayın
3. Proje adı: **uzem-studyo-plan** (veya istediğiniz isim)
4. Google Analytics'i istediğiniz gibi ayarlayın
5. "Proje Oluştur" butonuna tıklayın

## Adım 2: Realtime Database Ekleme

1. Sol menüden "Build" → "Realtime Database" seçin
2. "Veritabanı Oluştur" butonuna tıklayın
3. Lokasyon seçin (örn: europe-west1)
4. **Test modunda başlat** seçeneğini seçin (geliştirme için)
5. "Etkinleştir" butonuna tıklayın

## Adım 3: Web Uygulaması Kaydı

1. Proje ayarlarına gidin (⚙️ → Project Settings)
2. "Uygulamalarınız" bölümünde "</>" (Web) ikonuna tıklayın
3. Uygulama takma adı: **UZEM Takvim**
4. "Firebase Hosting'i ayarla" kutusunu işaretlemeyin
5. "Uygulamayı kaydet" butonuna tıklayın
6. Firebase config kodunu kopyalayın

Config kodu şuna benzer olacak:

```javascript
const firebaseConfig = {
  apiKey: "AIzaSyA...xyz",
  authDomain: "uzem-studyo-plan.firebaseapp.com",
  databaseURL: "https://uzem-studyo-plan-default-rtdb.firebaseio.com",
  projectId: "uzem-studyo-plan",
  storageBucket: "uzem-studyo-plan.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abc123"
};
```

## Adım 4: Güvenlik Kuralları (Opsiyonel - Production için)

Test modundan production'a geçerken Realtime Database kurallarını güncelleyin:

```json
{
  "rules": {
    "calendar": {
      ".read": "auth != null",
      ".write": "auth != null"
    }
  }
}
```

## Adım 5: index.html'i Güncelleme

Kopyaladığınız config'i `index.html` dosyasındaki `firebaseConfig` objesine yapıştırın (satır ~220 civarı)

## Test Etme

1. index.html'i bir tarayıcıda açın
2. Takvimde bir güne eğitmen eklemeyi deneyin
3. Firebase Console → Realtime Database'de verinin geldiğini kontrol edin
4. Başka bir tarayıcı/sekme açın → Gerçek zamanlı senkronizasyonu test edin

## Sorun Giderme

**Hata: Permission denied**
- Firebase Console'da Database kurallarını kontrol edin
- Test modunda olduğunuzdan emin olun

**Hata: Firebase not initialized**
- Config bilgilerini doğru kopyaladığınızdan emin olun
- Tarayıcı console'unda hata mesajlarını kontrol edin

**Senkronizasyon çalışmıyor**
- İnternet bağlantınızı kontrol edin
- databaseURL'nin doğru olduğundan emin olun
