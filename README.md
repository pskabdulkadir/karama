# Kutbul Zaman Network - MLM Yönetim Sistemi

Network Marketing yönetim sistemi - organize edilmiş src/ yapısı ile.

## 📁 Proje Yapısı

```
src/
├── components/          # React bileşenleri
│   ├── ui/             # Temel UI bileşenleri (Button, Card, vs.)
│   └── Header.tsx      # Ana header bileşeni
├── pages/              # Sayfa bileşenleri
│   ├── Dashboard.tsx   # Ana panel
│   ├── Login.tsx       # Giriş sayfası
│   ├── Landing.tsx     # Ana sayfa
│   └── ...            # Diğer sayfalar
├── routes/             # Routing yapılandırması
│   └── index.tsx       # Ana route tanımları
├── services/           # Veri servisleri
│   └── users-database.ts
├── layouts/            # Layout bileşenleri
│   ├── MainLayout.tsx
│   └── DashboardLayout.tsx
├── utils/              # Yardımcı fonksiyonlar
│   └── index.ts        # cn() utility fonksiyonu
├── constants/          # Sabitler ve tipler
│   └── mlm-types.ts    # MLM sistem tipleri
├── auth/               # Kimlik doğrulama
│   └── auth-service.ts # Auth service
├── global.css          # Global CSS
└── App.tsx            # Ana uygulama
```

## 🚀 Çalıştırma

```bash
npm run dev
```

## 🔑 Demo Giriş Bilgileri

**Kurucu/Admin:**

- Kullanıcı: `abdulkadirkqn`
- Şifre: `Abdulkadir1983`
- Ref No: `ak000001`

## 📋 Özellikler

- ✅ Organize edilmiş klasör yapısı
- ✅ Auth service ile kimlik doğrulama
- ✅ Responsive tasarım
- ✅ MLM kariyer sistemi (Emmare - Safiye)
- ✅ Dashboard ve panel sayfaları
- ✅ TypeScript desteği
- ✅ Tailwind CSS styling

## 🛠️ Teknolojiler

- **React 18** + TypeScript
- **Vite** - Build tool
- **Tailwind CSS** - Styling
- **Radix UI** - UI bileşenleri
- **React Router** - Routing
- **Lucide Icons** - İkonlar

## 📖 MLM Sistem

### Kariyer Seviyeleri

1. **Emmare** - Giriş seviyesi
2. **Levvame** - 2 direkt + $500
3. **Mülhime** - 4 aktif + $1500
4. **Mutmainne** - 10 ekip + $3000
5. **Radiyye** - 2 lider + $5000
6. **Mardiyye** - 50 toplam üye + $10000
7. **Safiye** - 3 lider + $25000 (Zirve)

### Bonus Sistemi

- **%25** Kariyer bonusları
- **%10** Sponsor bonusu
- **%5** Pasif bonus (sonsuz ekip)
- **%60** Sistem fonu

## 🔗 Panel Sayfaları

- `/panel/kariyerim` - Kariyer durumu
- `/panel/bonuslar` - Bonus geçmişi
- `/panel/yatirim-yap` - Yatırım işlemleri
- `/panel/simulasyon` - Kazanç simülasyonu

## 👥 Kullanıcı Rolleri

- **admin** - Kurucu (Abdulkadir Kan)
- **user** - Standart üye
- **distributor** - Distribütör
- **leader** - Lider

## 🎯 Ana Özellikler

1. **Dashboard** - Kullanıcı ana paneli
2. **Auth System** - Giriş/çıkış yönetimi
3. **MLM Structure** - Kariyer ve bonus sistemi
4. **Responsive Design** - Mobil uyumlu
5. **Type Safety** - TypeScript desteği
