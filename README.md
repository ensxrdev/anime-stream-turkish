<div align="center">

# 🎬 Anime Stream Turkish

**Modern Türkçe Anime Streaming Platformu**

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](./LICENSE)
[![Node.js](https://img.shields.io/badge/Node.js-18+-green.svg)](https://nodejs.org/)
[![Next.js](https://img.shields.io/badge/Next.js-14-black.svg)](https://nextjs.org/)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.0-blue.svg)](https://www.typescriptlang.org/)

</div>

---

## 📋 İçindekiler

- [Özellikler](#-özellikler)
- [Teknolojiler](#-teknolojiler)
- [Kurulum](#-kurulum)
- [Ortam Değişkenleri](#-ortam-değişkenleri)
- [Kullanım](#-kullanım)
- [Proje Yapısı](#-proje-yapısı)
- [Lisans](#-lisans)

---

## ✨ Özellikler

- 🎥 **Anime İzleme** - Yüksek kaliteli video oynatıcı ve bölüm takibi
- 👤 **Kullanıcı Sistemi** - Kayıt, giriş ve profil yönetimi
- 💬 **Yorum Sistemi** - Animelere yorum yapabilme
- ⭐ **Favori Listesi** - Beğendiğiniz animeleri kaydetme
- 📱 **Liste Yönetimi** - İzleme listesi oluşturma
- 🔔 **Bildirim Sistemi** - Yeni bölüm bildirimleri
- 🛡️ **Admin Paneli** - İçerik yönetimi için yönetici arayüzü
- 🎯 **Intro Atlama** - Otomatik intro atlama özelliği
- 🌙 **Karanlık Tema** - Göz yormayan modern tasarım

---

## 🛠 Teknolojiler

### Backend
- **Runtime:** Node.js
- **Framework:** Express.js
- **Veritabanı:** SQLite + Prisma ORM
- **Authentication:** JWT (Access & Refresh Token)
- **Güvenlik:** Helmet, Rate Limiting, CORS

### Frontend
- **Framework:** Next.js 14
- **UI:** React + TypeScript
- **Styling:** Tailwind CSS
- **State:** React Context API

---

## � Kurulum

### Gereksinimler

- [Node.js](https://nodejs.org/) (v18 veya üzeri)
- [npm](https://www.npmjs.com/) veya [yarn](https://yarnpkg.com/)
- [Git](https://git-scm.com/)

### 1. Projeyi Klonlayın

```bash
git clone https://github.com/ensxrdev/anime-stream-turkish.git
cd anime-stream-turkish
```

### 2. Bağımlılıkları Yükleyin

```bash
# Backend bağımlılıkları
npm install

# Frontend bağımlılıkları
cd frontend && npm install && cd ..
```

### 3. Ortam Değişkenlerini Ayarlayın

```bash
# .env.example dosyasını kopyalayın
cp .env.example .env

# .env dosyasını düzenleyin (aşağıdaki tabloya bakın)
```

### 4. Veritabanını Oluşturun

```bash
# Prisma migration
npx prisma migrate dev --name init

# Prisma client oluştur
npx prisma generate
```

### 5. Projeyi Başlatın

**Windows kullanıcıları için (otomatik):**
```bash
# Çift tıklayarak çalıştırın
start_ArianWatch.bat
```

**Manuel başlatma:**

```bash
# Terminal 1 - Backend (Port 4000)
npm run dev

# Terminal 2 - Frontend (Port 3000)
cd frontend && npm run dev
```

🌐 Tarayıcınızda **http://localhost:3000** adresini açın.

---

## ⚙️ Ortam Değişkenleri

Kök dizinde `.env` dosyası oluşturun:

| Değişken | Açıklama | Varsayılan |
|----------|----------|------------|
| `PORT` | Backend sunucu portu | `4000` |
| `DATABASE_URL` | SQLite veritabanı yolu | `file:./dev.db` |
| `JWT_ACCESS_SECRET` | Access token şifresi | - |
| `JWT_REFRESH_SECRET` | Refresh token şifresi | - |
| `LLAMA_API_URL` | LLaMA API endpoint (opsiyonel) | `http://localhost:8080/infer` |

### Örnek `.env` Dosyası

```env
PORT=4000
DATABASE_URL="file:./dev.db"
JWT_ACCESS_SECRET="guclu_gizli_anahtar_123"
JWT_REFRESH_SECRET="guclu_gizli_anahtar_456"
LLAMA_API_URL="http://localhost:8080/infer"
```

---

## 📁 Proje Yapısı

```
anime-stream-turkish/
├── 📂 frontend/              # Next.js frontend uygulaması
│   ├── 📂 src/
│   │   ├── 📂 components/    # React bileşenleri
│   │   ├── 📂 context/       # React Context (Auth, vb.)
│   │   ├── 📂 pages/         # Next.js sayfaları
│   │   └── 📂 styles/        # CSS dosyaları
│   └── 📄 package.json
│
├── 📂 src/                   # Backend kaynak kodları
│   ├── 📂 middleware/        # Express middleware'leri
│   ├── 📂 routes/            # API endpoint'leri
│   ├── 📂 utils/             # Yardımcı fonksiyonlar
│   └── 📄 server.ts          # Ana sunucu dosyası
│
├── 📂 prisma/                # Prisma şema ve migration
│   └── 📄 schema.prisma
│
├── 📄 .env.example           # Örnek ortam değişkenleri
├── 📄 package.json
├── 📄 LICENSE                # MIT Lisansı
└── 📄 README.md
```

---

## � Admin Yapma

Bir kullanıcıyı admin yapmak için:

```bash
npx ts-node make-admin.ts <kullanici_adi>
```

---

## 📜 API Endpoints

### Kimlik Doğrulama
- `POST /api/auth/register` - Kayıt
- `POST /api/auth/login` - Giriş
- `POST /api/auth/refresh` - Token yenileme

### Anime
- `GET /api/anime` - Tüm animeler
- `GET /api/anime/:id` - Anime detayı
- `POST /api/anime` - Anime ekle (Admin)

### Kullanıcı
- `GET /api/user/profile` - Profil bilgisi
- `GET /api/user/favorites` - Favoriler
- `GET /api/user/watchlist` - İzleme listesi

---

## 🤝 Katkıda Bulunma

1. Bu repoyu fork edin
2. Feature branch oluşturun (`git checkout -b feature/yeni-ozellik`)
3. Değişikliklerinizi commit edin (`git commit -m 'Yeni özellik eklendi'`)
4. Branch'inizi push edin (`git push origin feature/yeni-ozellik`)
5. Pull Request açın

---

## 📄 Lisans

Bu proje [MIT Lisansı](./LICENSE) altında lisanslanmıştır.

---

<div align="center">

**Geliştirici:** [ensxrdev](https://github.com/ensxrdev)

⭐ Bu projeyi beğendiyseniz yıldız vermeyi unutmayın!

</div>
