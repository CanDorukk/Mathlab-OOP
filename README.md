# MAUN Sosyal Medya Uygulaması

Muş Alparslan Üniversitesi öğrencileri için geliştirilmiş sosyal medya uygulaması.

## 📋 İçindekiler

- [Gereksinimler](#gereksinimler)
- [Kurulum](#kurulum)
- [Proje Yapısı](#proje-yapısı)
- [Şu Anda Bulunan Özellikler](#şu-anda-bulunan-özellikler)
- [Geliştirme](#geliştirme)
- [Bağımlılıklar](#bağımlılıklar)
- [Sorun Giderme](#sorun-giderme)
- [Katkıda Bulunma](#katkıda-bulunma)

> 📌 **Yapılacaklar listesi için**: [GOREVLER.md](GOREVLER.md) dosyasına bakın.

## 🔧 Gereksinimler

### Flutter SDK

Bu proje **Flutter 3.24.0** veya üzeri bir sürüm gerektirir.

Flutter sürümünüzü kontrol etmek için:
```bash
flutter --version
```

Flutter'ı yüklemek için: [Flutter Kurulum Kılavuzu](https://docs.flutter.dev/get-started/install)

### Geliştirme Ortamı

- **Dart SDK**: 3.4.3 veya üzeri
- **Android Studio** veya **VS Code** (Flutter eklentileri ile)
- **Android SDK** (Android geliştirme için)
  - **JDK**: Java Development Kit 11 veya üzeri (Android Studio ile birlikte gelir)
  - Android SDK Platform-Tools
  - Android SDK Build-Tools
- **Xcode** (iOS geliştirme için - sadece macOS)
  - Xcode 14 veya üzeri
  - CocoaPods

## 🚀 Kurulum

### 1. Projeyi Klonlayın

```bash
git clone <repository-url>
cd ekipuygulamasi
```

### 2. Flutter Bağımlılıklarını Yükleyin

```bash
flutter pub get
```

### 3. Flutter Doktor Kontrolü

Projenin düzgün çalıştığından emin olmak için:

```bash
flutter doctor
```

Tüm kontrollerin başarılı olduğundan emin olun. Özellikle şunları kontrol edin:
- ✅ Flutter SDK
- ✅ Android toolchain (Android Studio, Android SDK, JDK)
- ✅ VS Code veya Android Studio eklentileri
- ✅ Connected device (emülatör veya fiziksel cihaz)

Eksik bir şey varsa, `flutter doctor` komutu size nasıl düzeltebileceğinizi söyleyecektir.

### 4. Uygulamayı Çalıştırın

#### Android için:
```bash
flutter run
```

#### iOS için (sadece macOS):
```bash
flutter run
```

#### Belirli bir cihaz seçmek için:
```bash
flutter devices  # Mevcut cihazları listeler
flutter run -d <device-id>
```

## 📁 Proje Yapısı

```
lib/
├── core/                    # Temel yapılandırmalar ve yardımcılar
│   ├── constants/          # Sabitler (API URL'leri, anahtarlar vb.)
│   ├── errors/             # Hata sınıfları
│   ├── theme/              # Tema ayarları
│   └── utils/              # Yardımcı fonksiyonlar (validasyonlar vb.)
│
├── data/                    # Veri katmanı
│   └── models/             # Veri modelleri (User, Post, Comment vb.)
│
├── presentation/            # UI katmanı
│   └── screens/           # Ekranlar
│       ├── auth/          # Giriş/Kayıt ekranları
│       ├── explore/       # Keşfet sayfası
│       ├── feed/          # Ana feed sayfası
│       ├── main/          # Ana navigasyon ekranı
│       ├── messages/      # Mesajlaşma ekranları
│       ├── notifications/ # Bildirimler ekranı
│       ├── post/          # Gönderi ekranları
│       ├── profile/       # Profil ekranı
│       ├── search/        # Arama ekranı
│       ├── settings/      # Ayarlar ekranı
│       ├── splash/        # Splash ekranı
│       └── user/          # Kullanıcı profil ekranları
│
├── routes/                 # Navigasyon yapılandırması
│   └── app_router.dart
│
├── services/               # Servisler (API, Auth, Storage)
│   ├── api_service.dart
│   ├── auth_service.dart
│   └── storage_service.dart
│
├── widgets/                # Yeniden kullanılabilir widget'lar
│   ├── comment/           # Yorum widget'ları
│   ├── common/            # Ortak widget'lar
│   ├── message/           # Mesaj widget'ları
│   ├── notification/      # Bildirim widget'ları
│   ├── post/              # Gönderi widget'ları
│   ├── profile/           # Profil widget'ları
│   └── user/              # Kullanıcı widget'ları
│
└── main.dart              # Uygulama giriş noktası
```

## ✨ Şu Anda Bulunan Özellikler

Bu bölüm, uygulamada **şu anda çalışan ve fonksiyonel** olan özellikleri listeler.

### 🎨 Tema Sistemi
- ✅ **Light Mode (Açık Tema)**: Tamamen çalışıyor
- ✅ **Dark Mode (Karanlık Tema)**: Tamamen çalışıyor
- ✅ **Sistem Teması**: Sistem temasını otomatik takip ediyor
- ✅ **Tema Tercihi Kaydetme**: Kullanıcı tercihi SharedPreferences ile kalıcı olarak kaydediliyor
- ✅ **Anında Tema Değişimi**: Ayarlar sayfasındaki switch ile tema anında değişiyor

### 🔐 Kimlik Doğrulama
- ✅ **Splash Screen**: Uygulama açılışında gösteriliyor ve login ekranına yönlendiriyor
- ✅ **Login Ekranı**: UI hazır ve çalışıyor
- ✅ **Register Ekranı**: UI hazır ve çalışıyor
- ✅ **Admin Girişi**: `admin` / `admin` ile giriş yapılabiliyor (ana sayfaya yönlendiriyor)

### 🧭 Navigasyon
- ✅ **Bottom Navigation Bar**: 5 öğeli özel tasarım (Home, Explore, Gönderi Paylaş, Search, Profile)
- ✅ **Ortada Gönderi Paylaşma Butonu**: Navbar'ın üstünde konumlandırılmış kırmızı dairesel buton
- ✅ **Sayfa Geçişleri**: Tüm sayfalar arası navigasyon çalışıyor

### 📱 Ekranlar (UI Hazır)
- ✅ **Ana Feed Sayfası**: Gönderi listesi için UI hazır
- ✅ **Keşfet Sayfası**: Kategoriler ve trend gönderiler için UI hazır
- ✅ **Arama Sayfası**: Kullanıcı ve gönderi arama için UI hazır
- ✅ **Profil Sayfası**: Kullanıcı profili görüntüleme için UI hazır
- ✅ **Başka Kullanıcı Profil Sayfası**: Diğer kullanıcıların profillerini görüntüleme için UI hazır
- ✅ **Gönderi Paylaşma Sayfası**: Metin ve görsel paylaşma için UI hazır
- ✅ **Bildirimler Sayfası**: Bildirim listesi için UI hazır
- ✅ **Mesajlar Sayfası**: Konuşma listesi için UI hazır
- ✅ **Chat Sayfası**: Mesajlaşma ekranı için UI hazır
- ✅ **Ayarlar Sayfası**: Uygulama ayarları için UI hazır (tema switch çalışıyor)
- ✅ **Kullanıcı Arama Sayfası**: Kullanıcı arama sonuçları için UI hazır

### 🎨 UI Bileşenleri
- ✅ **PostCard Widget**: Gönderi kartı widget'ı hazır
- ✅ **ProfileHeader Widget**: Profil başlığı widget'ı hazır
- ✅ **CustomTextField Widget**: Özel text field widget'ı hazır
- ✅ **CustomButton Widget**: Özel buton widget'ı hazır
- ✅ **NotificationItem Widget**: Bildirim öğesi widget'ı hazır
- ✅ **UserCard Widget**: Kullanıcı kartı widget'ı hazır
- ✅ **MessageBubble Widget**: Mesaj balonu widget'ı hazır
- ✅ **CommentItem Widget**: Yorum öğesi widget'ı hazır

### 📊 Veri Modelleri
- ✅ **UserModel**: Kullanıcı veri modeli hazır
- ✅ **PostModel**: Gönderi veri modeli hazır
- ✅ **CommentModel**: Yorum veri modeli hazır
- ✅ **NotificationModel**: Bildirim veri modeli hazır
- ✅ **MessageModel**: Mesaj veri modeli hazır

### 🔧 Servisler (Yapı Hazır)
- ✅ **ApiService**: HTTP istekleri için servis yapısı hazır
- ✅ **AuthService**: Kimlik doğrulama servis yapısı hazır
- ✅ **StorageService**: Yerel depolama servis yapısı hazır

### ⚠️ Not
- Backend API entegrasyonu henüz tamamlanmamıştır. Tüm API çağrıları şu anda mock/simülasyon modunda çalışmaktadır.
- Veri modelleri ve servis yapıları hazırdır, backend hazır olduğunda kolayca entegre edilebilir.

## 🛠️ Geliştirme

### Yeni Özellik Ekleme

1. İlgili ekranı `lib/presentation/screens/` altında oluşturun
2. Gerekli modelleri `lib/data/models/` altında tanımlayın
3. API servislerini `lib/services/` altında güncelleyin
4. Route'ları `lib/routes/app_router.dart` dosyasına ekleyin

### Kod Stili

Proje `flutter_lints` paketini kullanmaktadır. Kodunuzu formatlamak için:

```bash
flutter format .
```

Lint hatalarını kontrol etmek için:

```bash
flutter analyze
```

### Test

Testleri çalıştırmak için:

```bash
flutter test
```

## 📦 Bağımlılıklar

### Ana Bağımlılıklar

- **http**: HTTP istekleri için
- **shared_preferences**: Yerel veri depolama için
- **image_picker**: Resim seçme için

### Bağımlılıkları Güncelleme

```bash
flutter pub upgrade
```

Yeni bağımlılık eklemek için `pubspec.yaml` dosyasını düzenleyin ve:

```bash
flutter pub get
```

## 🔐 Ortam Değişkenleri

API URL'lerini ve diğer yapılandırmaları `lib/core/constants/app_constants.dart` dosyasından düzenleyebilirsiniz.

## 🐛 Sorun Giderme

### Yaygın Sorunlar

1. **"No devices found" hatası**
   - Android emülatör veya fiziksel cihazın bağlı olduğundan emin olun
   - `flutter devices` komutu ile cihazları kontrol edin

2. **"Package not found" hatası**
   - `flutter pub get` komutunu çalıştırın
   - `pubspec.yaml` dosyasındaki bağımlılıkları kontrol edin

3. **Build hataları**
   - `flutter clean` komutunu çalıştırın
   - `flutter pub get` komutunu tekrar çalıştırın
   - Projeyi yeniden build edin

## 👥 Katkıda Bulunma

1. Yeni bir branch oluşturun (`git checkout -b feature/yeni-ozellik`)
2. Değişikliklerinizi commit edin (`git commit -m 'Yeni özellik eklendi'`)
3. Branch'inizi push edin (`git push origin feature/yeni-ozellik`)
4. Pull Request oluşturun

### Commit Mesajları

- `feat:` Yeni özellik
- `fix:` Hata düzeltmesi
- `docs:` Dokümantasyon
- `style:` Kod formatı
- `refactor:` Kod refaktörü
- `test:` Test ekleme/düzeltme

## 📝 Notlar

- Backend API entegrasyonu henüz tamamlanmamıştır. API servisleri mock verilerle çalışmaktadır.
- Bazı ekranlarda TODO yorumları bulunmaktadır. Bu alanlar geliştirme sırasında tamamlanacaktır.
- Yapılacaklar listesi için [GOREVLER.md](GOREVLER.md) dosyasına bakın.

## 📄 Lisans

Bu proje Muş Alparslan Üniversitesi için geliştirilmiştir.

## 📞 İletişim

Sorularınız için proje yöneticileri ile iletişime geçin.

---

**Not**: Bu proje aktif geliştirme aşamasındadır. Özellikler zamanla eklenecektir.
