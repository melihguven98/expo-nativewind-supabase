# ADR-001: Tech Stack

**Durum:** Kabul Edildi
**Tarih:** 2025-02-01

## Bağlam

iOS ve Android için tek codebase ile hızlı geliştirme yapılması gerekiyor.

## Karar

| Katman | Seçim | Neden |
|--------|-------|-------|
| Framework | Expo | Tek codebase, hızlı geliştirme |
| Routing | Expo Router | File-based, Next.js benzeri |
| Styling | NativeWind | Tailwind syntax, hızlı UI |
| State | Zustand | Minimal boilerplate |
| Backend | Supabase | All-in-one, PostgreSQL |

## Sonuçlar

- **Artılar:** Hızlı geliştirme, AI-friendly stack
- **Eksiler:** Supabase bağımlılığı
