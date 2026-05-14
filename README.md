# 🗂️ DevTrack — Proje Takip Sistemi

Tarayıcı tabanlı, sıfır bağımlılıklı bir **Kanban proje yönetim uygulaması**.  
Tüm veriler `localStorage`'da saklanır; sunucu veya veritabanı gerekmez.

---

## ✨ Özellikler

### 📁 Proje Yönetimi
- Birden fazla proje oluşturma, düzenleme ve silme
- Her projeye renk ve **bitiş tarihi** atama
- Sol menüde projenin bitişine **kaç hafta kaldığını** renkli badge ile görme
  - 🟢 6+ hafta → Yeşil
  - 🟡 3–5 hafta → Sarı
  - 🔴 0–2 hafta → Kırmızı
  - ⬛ Süre doldu → Gri

### ✅ Görev (Kanban) Yönetimi
- **Yapılacak / İşlemde / Tamamlandı** sütunları
- Görev eklerken:
  - Başlık ve açıklama
  - Etiket: `Görev`, `Feature`, `Bug`, `Refactor`, `Design`
  - Öncelik: `Normal`, `Yüksek`, `Düşük`
  - Süre (gün)
  - Bağlı proje adımı seçimi
- Görevleri **sürükle-bırak** ile sütunlar arasında taşıma
- Mevcut görevi **düzenleme** (kalem ikonu)
- Görev silme

### 🚩 Proje Adımları (Faz Takibi)
- Her projeye adımlar ekleme: ad, başlangıç ve bitiş tarihi
- Sağ panel (timeline) görünümü
- Otomatik durum hesaplama:
  - 🟢 **Tamamlandı** — bitiş tarihi geçmiş
  - 🔵 **Devam Ediyor** — bugün başlangıç–bitiş arasında
  - ⬛ **Bekliyor** — henüz başlamamış
- Adım başına **kaç gün** ayrıldığı
- Adıma bağlı **kaç görev** olduğu

---

## 🚀 Kullanım

Kurulum gerektirmez. Doğrudan tarayıcıda açın:

```
index.html
```

veya bir local server ile sunun:

```bash
# Python ile
python -m http.server 8080

# Node.js ile
npx serve .
```

---

## 🗃️ Veri Yapısı

Tüm veriler `localStorage` anahtarı **`devtrack`** altında JSON olarak saklanır:

```json
{
  "projects": [
    {
      "id": "abc123",
      "name": "Proje Adı",
      "color": "#6366f1",
      "deadline": "2026-12-31"
    }
  ],
  "tasks": {
    "abc123": [
      {
        "id": "xyz789",
        "title": "Görev başlığı",
        "text": "Açıklama",
        "tag": "feature",
        "priority": "high",
        "duration": "5",
        "phaseId": "phase001",
        "status": "yapilacak"
      }
    ]
  },
  "phases": {
    "abc123": [
      {
        "id": "phase001",
        "name": "Fizibilite",
        "start": "2026-01-01",
        "end": "2026-02-01"
      }
    ]
  }
}
```

---

## 🛠️ Teknoloji

| Katman | Teknoloji |
|---|---|
| Yapı | HTML5 |
| Stil | Vanilla CSS (dark theme) |
| Mantık | Vanilla JavaScript (ES6+) |
| İkonlar | Font Awesome 6 |
| Fontlar | Google Fonts — Inter |
| Depolama | localStorage |

---

## 👤 Geliştirici

**Emre Karabek** — [karabek@gmail.com](mailto:karabek@gmail.com)  
AssemCorp Electronic

---

## 📄 Lisans

Bu proje özel kullanım amaçlıdır. Tüm hakları saklıdır.
