# Numarine 37XP · WebAR
## Kurulum ve Deploy

---

## Proje yapısı

```
numarine-mindar/
├── index.html          ← Ana uygulama
├── vercel.json         ← Vercel config (kamera izni için gerekli)
├── assets/
│   └── yacht.glb       ← 3D model (zaten hazır)
└── targets/
    └── numarine-brochure.mind  ← Image target (aşağıda nasıl üretileceği var)
```

---

## ADIM 1 — Image Target (.mind dosyası) üret

MindAR image target, broşür görselinden üretilir.

1. https://hiukim.github.io/mind-ar-js-doc/tools/compile adresine git
2. Broşürünüzün yüksek çözünürlüklü görselini yükle (JPG/PNG, min 800px)
3. "Compile" tıkla → `targets.mind` dosyası indir
4. Bu dosyayı `targets/numarine-brochure.mind` olarak kaydet

---

## ADIM 2 — Dosyaları yerleştir

```
assets/yacht.glb       → zaten var
targets/numarine-brochure.mind  → yukarıda üretildi
```

---

## ADIM 3 — GitHub'a yükle

```bash
git init
git add .
git commit -m "Numarine 37XP AR"
git remote add origin https://github.com/KULLANICI_ADI/numarine-ar.git
git push -u origin main
```

---

## ADIM 4 — Vercel'e deploy et

1. vercel.com → "Add New Project"
2. GitHub repo'yu seç → Import
3. Deploy tıkla
4. URL alırsın: `https://numarine-ar.vercel.app`

---

## ADIM 5 — QR Kod

URL hazır olunca:
- qr-code-generator.com → URL gir → Numarine logosuyla özelleştir → indir → broşüre bas

---

## Deneyim akışı

```
QR okunur → tarayıcı açılır
    ↓
Mod seçimi: Broşürü Tarat / Zemine Yerleştir
    ↓
Kamera izni
    ↓
[Broşür] Sayfaya tut → tekne belirir üzerinde
[Zemin]  Ekrana dokun → tekne yerleşir
    ↓
Arka plan blur efekti
    ↓
Hotspot'lar sırayla belirir
    ↓
Otomatik spec turu (Motor→Performans→Kabin→Köprüüstü)
    ↓
Kullanıcı kontrol: döndür, ölçek, tüm özellikler, paylaş
```
