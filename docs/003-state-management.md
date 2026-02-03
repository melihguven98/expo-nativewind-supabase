# ADR-003: State Management

**Durum:** Kabul Edildi
**Tarih:** 2025-02-01

## Bağlam

Uygulama genelinde state yönetimi stratejisi belirlenmeli.

## Karar

| State Tipi | Çözüm |
|------------|-------|
| Global (auth, theme) | Zustand |
| Server data | Fetch + Zustand |
| Form | React Hook Form |
| Local | useState |

## Sonuçlar

- **Artılar:** Basit, anlaşılır, test edilebilir
- **Eksiler:** Birden fazla pattern öğrenilmeli
