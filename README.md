# 🗺️ Danske Attraktioner · Stampbog App

En interaktiv app til at besøge og markere danske attraktioner med **geo-låsning via fotografie**. Tager billeder af attraktioner med GPS-data, og appen bekræfter automatisk at du var der.

**Live demo:** https://danske-attraktioner.netlify.app

---

## ✨ Features

✅ **Interaktivt Leaflet-kort** - Vis alle attraktioner inden for valgt radius
✅ **Geo-låsning** - Tag foto på stedet → appen bekræfter GPS-position (100m tolerance)
✅ **Region-tracking** - Se hvor mange du mangler på Jylland/Fyn/Sjælland/Øerne
✅ **Pris-info** - Entré-priserne for hver attraktion
✅ **Google Maps rutevejledning** - "Kør hertil fra min position"
✅ **PWA installering** - Installér på hjemmeskærm som app
✅ **Offline-support** - Alt virker offline (localStorage)
✅ **30+ attraktioner** - Fra alle danske regioner

---

## 🚀 Sådan bruger du den

### **Desktop/Web**
1. Åbn https://danske-attraktioner.netlify.app
2. Tillad lokation-adgang
3. Brug radius-slider til at finde attraktioner nær dig
4. Klik en attraktion → se detaljer + rutevejledning

### **Mobil (iOS/Android)**
1. Åbn appen i browser
2. Se opfordringen "Installér app" eller brug menu → "Installér"
3. Appen er nu på din hjemmeskærm
4. Tag billeder **med GPS aktiveret** for geo-låsning

### **Geo-låsning (vigtig!)**
```
1. GPS skal være AKTIVERET på telefonen
2. Browser skal have lokation-tilladelse
3. Kamera-appen skal gemme GPS i foto (EXIF)
4. Tag billede på attraktionen (skal være inden for 100m)
5. ✅ Automatisk markeret som "besøgt" med 🔒 Geo-låst
```

**GPS-aktivering:**
- **iPhone**: Settings → Privacy → Location → aktivér for Safari/browser
- **Android**: Settings → Apps → Kamera → Permissions → Location

---

## 📱 Attraktioner

**Fyn (9 steder)**
- Den Gamle Lillebeltsbro, Nyborg Slot, Egeskov Slot, Jernbanemuseet osv.

**Jylland (10 steder)**
- LEGOLAND, Jelling Stenene, ARoS, Moesgård Museum osv.

**Sjælland (8 steder)**
- Tivoli, Kronborg, Frederiksborg Slot, Nationalmuseet osv.

**Øerne (3 steder)**
- Møn's Klint, Hammershus, Christiansborg Slot

**Total: 30+ attraktioner**

---

## 🔧 Teknologi

- **Frontend**: HTML5, CSS3, Vanilla JavaScript
- **Kort**: Leaflet.js + OpenStreetMap
- **GPS-læsning**: exifr.js (EXIF-data fra fotos)
- **Lagring**: localStorage (offline)
- **PWA**: Manifest.json + Service Worker

---

## 📦 Setup (lokalt)

```bash
# 1. Clone repo
git clone https://github.com/LadepriserDK/Danske-Attraktioner.git
cd Danske-Attraktioner

# 2. Start lokal server (Python)
python -m http.server 8000
# eller Node.js
npx http-server

# 3. Åbn http://localhost:8000
```

---

## 🌐 Deploy til Netlify

### **Automatisk fra GitHub** (anbefalet)
1. Push til GitHub
2. Netlify auto-deployer
3. URL: https://danske-attraktioner.netlify.app

### **Manuel upload**
1. Drag `index.html` + `manifest.json` til Netlify
2. ✅ Live på egen URL

---

## 🗂️ Fil-struktur

```
Danske-Attraktioner/
├── index.html          ← Hele appen (HTML + CSS + JS)
├── manifest.json       ← PWA installering
└── README.md          ← Du er her
```

**Sådan tilføjer du flere attraktioner:**

Rediger `index.html` og find `const ATTRACTIONS = [` - tilføj nye objekter:

```javascript
{ 
  id: 'unik-id',
  name: 'Attraktion Navn',
  category: 'Slot',
  region: 'Fyn',
  lat: 55.123,
  lng: 9.456,
  city: 'By',
  price: '150 kr',
  image: '🏰',
  desc: 'Kort beskrivelse'
}
```

---

## 💾 Data-lagring

Alt gemmes lokalt i **localStorage**:
- `visited_[id]` - Besøgte attraktioner
- `geo_locked_[id]` - Geo-bekræftede besøg
- `photos_[id]` - Dine fotos (base64 encoded)

**Ingen data sendes til serveren!** Fuldstændigt privat.

---

## 🐛 Fejlrapportering

**Geo-låsning virker ikke?**
- Tjek at GPS er aktiveret
- Tjek browser-tilladelser
- Billede skal indeholde EXIF GPS-data

**Kort vises ikke?**
- Tjek internet-forbindelse
- Tillad lokation-adgang
- Prøv anden browser

---

## 📝 Licens

Open source - brug frit!

---

## 👤 Kontakt

Spørgsmål? Ønsker du flere attraktioner? [Åbn et issue](https://github.com/LadepriserDK/Danske-Attraktioner/issues)

---

**Made with ❤️ for Danmark turister**
