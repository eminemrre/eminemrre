# SecurifyISG Landing Page

[securifyisg.com](https://securifyisg.com) için ürün tanıtım (landing) sayfası. Panelin kendi marka kimliğiyle birebir uyumlu: koyu tema (`#08090c`), zümrüt aksan (`#18e29b`), Space Grotesk / Inter / JetBrains Mono.

Tek dosyalık statik bir sayfadır; framework, build adımı ve JavaScript gerektirmez.

## İçerik

| Dosya | Açıklama |
|---|---|
| `index.html` | Sayfanın tamamı (HTML + CSS, JS yok) |
| `fonts/` | Panelin kendi woff2 subset'leri (self-hosted — Google Fonts'a istek atılmaz, KVKK dostu) |
| `favicon.ico` | Panel ile aynı favicon |
| `og.png` | Sosyal medya paylaşım görseli (1200×630) |

## Bölümler

Hero (canlı panel maketi ile) → metrik bandı → 6 özellik → 16 modüllük harita (Canlı / Geliştiriliyor durum çipleriyle) → KPI formülleri → 3 adım → SSS → CTA. Modül listesi ve KPI tanımları paneldeki gerçek modüllerden alınmıştır.

## Yayına alma

**Seçenek A — Ayrı statik site (önerilen başlangıç):** Bu klasörü Vercel/Netlify'a statik olarak bağlayın. Paneli `app.securifyisg.com` altına taşıyıp landing'i `securifyisg.com` köküne alabilirsiniz.

**Seçenek B — Mevcut Next.js paneline gömme:** `fonts/`, `og.png` ve `favicon.ico` dosyalarını `public/` altına kopyalayın; `index.html` içeriğini bir marketing route'una (`app/(marketing)/page.tsx`) taşıyın. Panel zaten aynı fontları yüklediği için `fonts/` klasörünü atlayıp `next/font` değişkenlerini kullanabilirsiniz.

## Yayına almadan önce kontrol edin

- [ ] **E-posta adresi:** CTA'lardaki `info@securifyisg.com` varsayılandır — gerçek iletişim adresinizle değiştirin (3 yerde geçer).
- [ ] **Panel bağlantısı:** "Panele Giriş" düğmeleri `https://securifyisg.com` adresine gider; panel farklı bir alt alan adına taşınırsa güncelleyin.
- [ ] **og.png:** `https://securifyisg.com/og.png` yolundan erişilebilir olmalı (meta etiketi mutlak URL bekler).
