# UZEM İş Takvimi - Stüdyo Çekim Planlama Sistemi

## 🎬 Proje Hakkında

UZEM İş Takvimi, Google Sheets + Firebase tabanlı gerçek zamanlı stüdyo çekim planlama uygulamasıdır.

## ✨ Özellikler

- ✅ **Responsive React Takvimi** - Sadece Pazartesi-Cuma gösterimi
- ✅ **Ay & Yıl Seçimi** - Dinamik takvim oluşturma
- ✅ **Firebase Realtime Database** - Gerçek zamanlı senkronizasyon
- ✅ **Google Sheets Entegrasyonu** - Çift yönlü veri senkronizasyonu
- ✅ **Eğitmen Atama Sistemi** - Otomatik tamamlama önerili
- ✅ **Sabah & Öğle Seansları** - İki farklı çekim süresi
- ✅ **Filtreleme & Arama** - Eğitmen adına göre filtre
- ✅ **Detaylı Raporlama** - İstatistikler ve grafikler
- ✅ **Modern Türkçe UI** - Gradient tasarım, responsive
- ✅ **Bugün Vurgusu** - Mevcut tarih renk kodlaması

## 🚀 Kurulum

### 1. Firebase Kurulumu

Firebase Console'da yeni proje oluşturun:
https://console.firebase.google.com/

1. Proje oluştur → "UZEM Stüdyo Plan"
2. Realtime Database ekle → Test modunda başlat
3. Proje ayarları → Web uygulaması ekle
4. Config bilgilerini kopyala

### 2. Firebase Config Güncelleme

`index.html` dosyasındaki Firebase config'i güncelleyin:

```javascript
const firebaseConfig = {
    apiKey: "YOUR_API_KEY",
    authDomain: "your-project.firebaseapp.com",
    databaseURL: "https://your-project-default-rtdb.firebaseio.com",
    projectId: "your-project-id",
    storageBucket: "your-project.appspot.com",
    messagingSenderId: "YOUR_SENDER_ID",
    appId: "YOUR_APP_ID"
};
```

### 3. Google Sheets Entegrasyonu

Google Cloud Console'da API aktive edin:
https://console.cloud.google.com/apis/library

1. Google Sheets API'yi aktive et
2. Service Account oluştur
3. JSON key dosyasını indir
4. Sheets dosyanızı service account email ile paylaş

### 4. Deploy

#### GitHub Pages ile:

```bash
git add .
git commit -m "Initial commit"
git push origin main
```

GitHub repo → Settings → Pages → Source: main branch

#### Netlify ile:

1. Netlify'a giriş yap
2. "New site from Git" → GitHub repo seç
3. Deploy!

## 📊 Veri Yapısı

### Firebase Realtime Database

```json
{
  "calendar": {
    "2025-11-3": {
      "morning": ["Elif Egüz", "Simay Beliç"],
      "afternoon": ["Turgay Bekşen"]
    },
    "2025-11-4": {
      "morning": ["Zeynep İris Bilen"],
      "afternoon": ["Bülent Eren"]
    }
  }
}
```

### Google Sheets Format

| Tarih | Sabah Eğitmenler | Öğle Eğitmenler |
|-------|------------------|-----------------|
| 2025-11-03 | Elif Egüz, Simay Beliç | Turgay Bekşen |
| 2025-11-04 | Zeynep İris Bilen | Bülent Eren |

## 🎨 Kullanım

### Eğitmen Ekleme

1. İlgili günün kutusuna tıklayın
2. "Eğitmen ekle" alanına yazmaya başlayın
3. Otomatik tamamlama listesinden seçin
4. Enter veya tıklayın

### Eğitmen Silme

Eğitmen adının yanındaki **×** butonuna tıklayın

### Filtreleme

Üstteki "Filtre" kutusuna eğitmen adı yazın

### Rapor Görüntüleme

"📊 Rapor Göster" butonuna tıklayın:
- Toplam gün sayısı
- Dolu/boş seans sayıları
- Doluluk oranı
- Eğitmen başına çekim günleri
- İnteraktif grafik

## 🔧 Geliştirme

### Eğitmen Listesi Güncelleme

`index.html` içinde `TRAINERS` dizisini düzenleyin:

```javascript
const TRAINERS = [
    "Yeni Eğitmen",
    "Başka Eğitmen",
    // ...
];
```

### Tema Renkleri

CSS'te gradient renklerini değiştirin:

```css
.header {
    background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
}
```

## 📱 Responsive Tasarım

- Desktop: 5 kolon (Pazartesi-Cuma)
- Tablet: 3 kolon
- Mobile: 2 kolon

## 🛠️ Teknolojiler

- **Frontend:** React 18 (CDN)
- **UI:** Vanilla CSS (Gradient tasarım)
- **Charts:** Chart.js 4
- **Backend:** Firebase Realtime Database
- **Storage:** Google Sheets API
- **Deploy:** GitHub Pages / Netlify

## 📄 Lisans

MIT License

## 👤 Geliştirici

UZEM Ekibi

## 🤝 Katkıda Bulunma

1. Fork yapın
2. Feature branch oluşturun (`git checkout -b feature/amazing`)
3. Commit yapın (`git commit -m 'feat: Add amazing feature'`)
4. Push edin (`git push origin feature/amazing`)
5. Pull Request açın

## 📞 İletişim

Sorularınız için: uzem@example.com

---

**Not:** Firebase ve Google Sheets API anahtarlarınızı güvenli tutun!
