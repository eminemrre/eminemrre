# SecurifyISG Landing Page

[securifyisg.com](https://securifyisg.com) için ürün tanıtım (landing) sayfası. Panelin kendi marka kimliğiyle birebir uyumlu: koyu tema (`#08090c`), zümrüt aksan (`#18e29b`), Space Grotesk / Inter / JetBrains Mono.

Statik bir sayfadır; framework ve build adımı gerektirmez. Tüm bağımlılıklar (fontlar dahil) yereldir — dış CDN'e tek istek atılmaz.

## Teknoloji

- **GSAP 3.13** + **ScrollTrigger** + **SplitText** — hero zaman çizelgesi (satır satır başlık reveal'ı, KPI sayaçları, sparkline çizimi), kaydırma reveal'ları, aktif bölüm vurgusu. GSAP artık tüm eklentileriyle ücretsiz.
- **Lenis 1.3** — pürüzsüz kaydırma, ScrollTrigger ile senkron.
- **Vanilla canvas** — hero'da partikül + tarama çizgisi efekti (DPR duyarlı, görünüm dışında duraklar).
- Maket eğimi (pointer tilt), kartlarda imleç spot ışığı, modül marquee'si, maket içi canlı bildirim döngüsü.

**Erişilebilirlik / dayanıklılık:** `prefers-reduced-motion` ve JS'siz tarayıcılarda sayfa animasyonsuz ama eksiksiz görünür (progressive enhancement); kütüphaneler yüklenemezse içerik otomatik görünür kalır. `?static=1` parametresi animasyonları tamamen kapatır (ekran görüntüsü/test için).

## İçerik

| Dosya | Açıklama |
|---|---|
| `index.html` | Sayfanın tamamı (HTML + CSS + animasyon kodu) |
| `vendor/` | GSAP, ScrollTrigger, SplitText, Lenis (self-hosted) |
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
