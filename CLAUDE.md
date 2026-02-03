# CLAUDE.md

> Claude Code için proje bağlamı.

## Proje

**Ad:** [Proje Adı]
**Açıklama:** [Ne yapar?]
**Platform:** iOS & Android (Expo)

## Tech Stack

- **Frontend:** Expo SDK 54, Expo Router, NativeWind
- **State:** Zustand
- **Backend:** Supabase (PostgreSQL, Auth, Storage)

## Proje Yapısı

```
app/          # Sayfalar (file-based routing)
components/   # UI bileşenleri
lib/          # Supabase client, API fonksiyonları
store/        # Zustand store'ları
types/        # TypeScript tipleri
utils/        # Yardımcı fonksiyonlar
```

## Kurallar

- TypeScript strict mode, `any` yasak
- Functional components only
- Dosya: kebab-case, Component: PascalCase
- NativeWind/Tailwind ile styling
- Hata durumlarını handle et

## Komutlar

```bash
npm start       # Dev server
npm run ios     # iOS
npm run android # Android
npm run lint    # Lint check
```

## Ortam Değişkenleri

```
EXPO_PUBLIC_SUPABASE_URL=
EXPO_PUBLIC_SUPABASE_ANON_KEY=
```
