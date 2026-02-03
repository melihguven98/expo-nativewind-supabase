# ADR-002: Authentication

**Durum:** Kabul Edildi
**Tarih:** 2025-02-01

## Bağlam

Kullanıcı girişi için sosyal login ve email desteği gerekiyor.

## Karar

**Supabase Auth** kullanılacak:
- Google OAuth (Android için)
- Apple Sign-In (iOS için zorunlu)
- Email/Password (fallback)

Token'lar AsyncStorage'da saklanacak, Supabase SDK otomatik yenileyecek.

## Sonuçlar

- **Artılar:** Hazır çözüm, güvenli, kolay entegrasyon
- **Eksiler:** Supabase'e bağımlılık
