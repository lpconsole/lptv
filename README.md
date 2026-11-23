<div align="center">

# 📺 LPTv — Android TV & Mobil Canlı TV / Radyo Oynatıcı

**Reklamsız, hesapsız, takip içermeyen; Android TV kumandası ve dokunmatik cihazlar için sıfırdan tasarlanmış yüksek performanslı native medya deneyimi.**

<p>
  <a href="https://github.com/lpconsole/lptv/releases">
    <img src="https://img.shields.io/badge/Version-1.0.0-2F80FF?style=for-the-badge&logo=github&logoColor=white" alt="Version">
  </a>
  <a href="https://developer.android.com">
    <img src="https://img.shields.io/badge/Android-8.0%2B%20(API%2026%2B)-00E676?style=for-the-badge&logo=android&logoColor=black" alt="Platform">
  </a>
  <img src="https://img.shields.io/badge/Kotlin-Jetpack%20Compose-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white" alt="Tech">
  <img src="https://img.shields.io/badge/License-All%20Rights%20Reserved-EF4444?style=for-the-badge" alt="License">
</p>

[![En Son Sürümü İndir](https://img.shields.io/github/v/release/lpconsole/lptv?style=for-the-badge&logo=android&logoColor=black&color=00E676&label=%C4%B0ndir%20(APK))](https://github.com/lpconsole/lptv/releases/latest/download/app-release.apk)

</div>

---

## ✨ Öne Çıkan Özellikler

### 📡 Akıllı Yayın & Kesintisiz Oynatma
- **Dinamik Yedek Yayın Altyapısı (Backup Streams):** Ana yayın koptuğunda veya yanıt vermediğinde oynatıcı otomatik olarak sıradaki yedek kaynağa geçer.
- **Manuel Kaynak, Ses & Altyazı Seçici:** Oynatıcı seçeneklerinden kanalın alternatif yayın linkleri (`Ana Yayın`, `Yedek 1`, `Yedek 2`...), ses dilleri ve altyazılar arasında anında geçiş yapılabilir.
- **12s Bekçi Zamanlayıcısı (Watchdog) & EOF Koruması:** Donmuş akışları veya canlı yayında gelen hatalı bitiş sinyallerini yakalayarak yayını otomatik toparlar.
- **Media3 (ExoPlayer) + SurfaceView:** WebView değil, donanım hızlandırmalı saf native Android video ve ses motoru kullanır.

### 🎮 Hem Kumanda (D-Pad) Hem Dokunmatik Uyumlu (`DualControl`)
- **Özel Kanal Sıralama Modu ("Tut ve Taşı"):**
  - **Kumandada:** *Sırala* moduna geçip **OK** ile kanalı tutun, **▲ / ▼** tuşlarıyla taşıyın ve tekrar **OK** ile bırakın.
  - **Dokunmatikte:** Satır yanındaki **▲ / ▼** oklarıyla kanalları tek dokunuşla yukarı/aşağı kaydırın.
  - Yapılan sıralamalar **Room** veritabanında kalıcı olarak saklanır ve istenildiğinde tek tıkla sıfırlanabilir.
- **Hızlı İşlem Menüsü (Uzun Basma):** Kanal üzerinde **OK** tuşuna basılı tutarak veya dokunarak uzun basıp `Favorilere Ekle / Çıkar`, `Sıralamayı Düzenle` ve `Kanalı Aç` seçeneklerine ulaşın.
- **Tek Dokunuşla Favoriler & Zap Desteği:** Sayısal tuşlarla direkt kanal numarasına atlama (`Zap`), Son İzlenenler geçmişi ve tek dokunuşla favori yıldızı.

### 📻 Zengin TV & Radyo Deneyimi
- **TV & FM Radyo Tek Çatıda:** Canlı televizyon kanalları ve dünya genelinden radyo istasyonları ayrı ve düzenli sekmelerde sunulur.
- **Canlı Program Rehberi (EPG):** TV kanallarında o an yayınlanan program bilgisi arka planda düşük öncelikle çekilip ekranda gösterilir.
- **Radyo Modu Özelleştirmeleri:** Hareketli GIF poster arka planları, ses dalgası görselleştiricisi (Visualizer) ve canlı şarkı sözü (Lyrics) desteği.
- **Güçlü Arama & Filtreleme:** FTS4 tam metin arama, ülke ve kategori filtreleri, çoklu sıralama modları ve isteğe bağlı içerik filtreleme.

### 🔒 Gizlilik & Güncelleme
- **Sıfır Reklam, Sıfır Takip:** Hesap oluşturma, reklam, analitik veya kullanıcı takibi kesinlikle yoktur.
- **Uygulama İçi Güncelleyici:** GitHub Releases tabanlı manifest kontrolü sayesinde yeni sürümler doğrudan uygulama içinden indirilip kurulabilir.

---

## 🛠️ Teknoloji Yığını

| Katman | Kullanılan Teknolojiler |
| :--- | :--- |
| **Dil & Arayüz** | Kotlin, Jetpack Compose, TV Material 3, Material 3 |
| **Oynatıcı** | AndroidX Media3 (`ExoPlayer`, HLS, OkHttp DataSource, MediaSession) |
| **Mimari & DI** | MVVM, Hilt, Kotlin Coroutines & StateFlow |
| **Veritabanı & Ağ** | Room (SQLite + FTS4), Retrofit, OkHttp, Coil (GIF/SVG) |

---

## 📦 Kurulum ve Derleme

> [!NOTE]
> `v1.0.0` ile birlikte resmi paket adı **`com.lpconsole.lptv`** olarak güncellenmiştir. Eski sürümlerden (`v0.2.8` ve öncesi) geçişte temiz kurulum önerilir.

### Yerel Derleme (Debug APK)

```powershell
cmd /c gradlew.bat assembleDebug --console=plain
```

Çıktı konumu:
```text
app/build/outputs/apk/debug/app-debug.apk
```

---

## 🔄 Uygulama İçi Güncelleme Sistemi

Uygulama, GitHub Releases üzerinden sunulan `update.json` manifestini kontrol eder ve `versionCode` karşılaştırmasına göre kullanıcıya güncelleme bildirimi gösterir.

- Paket Adı: `com.lpconsole.lptv`
- Minimum Android Sürümü: **Android 8.0 (API 26)**
- Hedef SDK: **API 36**

---

## 🌐 Veri Kaynakları

- **TV Kanalları:** [`iptv-org`](https://iptv-org.github.io)
- **Radyo İstasyonları:** [`Radio Browser API`](https://www.radio-browser.info)

> *Bu uygulama kendi sunucularında medya içeriği barındırmaz; yalnızca herkese açık API'lerden gelen yayın akışlarını oynatır.*
