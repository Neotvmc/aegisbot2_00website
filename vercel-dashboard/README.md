# AegisBot Dashboard - Vercel Deployment

## 📋 Übersicht

Dieses Verzeichnis enthält alle Dateien für das AegisBot Dashboard, optimiert für Vercel-Deployment. Das Dashboard bietet eine moderne, responsive Benutzeroberfläche mit Echtzeit-Statistiken und vollständiger Befehlsübersicht.

## 🗂️ Dateistruktur

```
vercel-dashboard/
├── package.json          # Node.js Dependencies
├── vercel.json           # Vercel Deployment-Konfiguration
├── README.md             # Diese Datei
├── api/
│   └── server.js         # Express.js API Server
└── public/
    ├── index.html        # Haupt-HTML-Datei
    ├── style.css         # CSS Styling
    └── script.js         # JavaScript Funktionalität
```

## 🚀 Deployment auf Vercel

### 1. Repository vorbereiten
Kopiere den gesamten `vercel-dashboard` Ordner in dein GitHub Repository.

### 2. Vercel Projekt erstellen
1. Gehe zu [vercel.com](https://vercel.com)
2. Melde dich mit deinem GitHub Account an
3. Klicke auf "New Project"
4. Wähle dein Repository aus
5. Setze **Root Directory** auf `vercel-dashboard`

### 3. Deployment-Einstellungen
- **Framework Preset**: Other
- **Root Directory**: `vercel-dashboard`
- **Build Command**: Leer lassen
- **Output Directory**: `public`

### 4. Deploy
Klicke auf "Deploy" - Vercel erkennt automatisch die `vercel.json` Konfiguration.

## 🔗 API Endpoints

Das Dashboard stellt folgende Endpoints bereit:

- `GET /api/status` - Bot-Status und Statistiken
- `POST /api/status` - Bot-Status aktualisieren (für Bot-Integration)
- `GET /api/health` - Health Check

## 📊 Features

✅ **Echtzeit Bot-Status**
- Online/Offline Anzeige mit Pulse-Animation
- Uptime Tracking
- Automatische Status-Updates

✅ **System-Monitoring**
- Live RAM-Verbrauch mit Progress Bar
- CPU-Informationen (Modell, Kerne, Architektur)
- Server-Performance Metriken

✅ **Bot-Statistiken**
- Aktive Nutzer mit animierten Zahlen
- Gruppen-Anzahl
- Registrierte Benutzer
- Haustier-System Statistiken

✅ **Vollständige Befehlsliste**
- 13 Kategorien (Economy, Games, Pets, etc.)
- 80+ Befehle mit Beschreibungen
- Suchbare und kategorisierte Darstellung

✅ **Modernes Design**
- Dark Theme mit Gradient-Akzenten
- Responsive Layout (Desktop, Tablet, Mobile)
- Smooth Scrolling Navigation
- Hover-Effekte und Animationen
- Floating Background Shapes

✅ **Auto-Updates**
- Automatische Datenaktualisierung alle 30 Sekunden
- Live-Zeitstempel der letzten Aktualisierung
- Manueller Refresh-Button mit Spin-Animation

## 🎨 Design-Features

- **Farbschema**: Türkis-Lila Gradient (#00d4aa → #6c5ce7)
- **Typografie**: Inter Font für moderne Lesbarkeit
- **Animationen**: Floating Shapes, Pulse-Effekte, Smooth Transitions
- **Layout**: CSS Grid für responsive Anordnung
- **Icons**: Font Awesome 6.4.0 für konsistente Symbole

## 🔧 Lokale Entwicklung

Für lokale Tests:

```bash
# In den vercel-dashboard Ordner wechseln
cd vercel-dashboard

# Dependencies installieren
npm install

# Server starten
npm start
```

Das Dashboard ist dann unter `http://localhost:3000` erreichbar.

## 📱 Responsive Design

Das Dashboard ist vollständig responsive:

- **Desktop** (>768px): Vollständiges Grid-Layout
- **Tablet** (768px-480px): Angepasste Spaltenanzahl
- **Mobile** (<480px): Single-Column Layout

## 🔄 Bot-Integration

Für Live-Daten von deinem Bot, sende POST-Requests an `/api/status`:

```javascript
// Beispiel Bot-Integration
const updateDashboard = async (botData) => {
    await fetch('https://your-dashboard.vercel.app/api/status', {
        method: 'POST',
        headers: { 'Content-Type': 'application/json' },
        body: JSON.stringify({
            isOnline: true,
            totalUsers: botData.users,
            totalGroups: botData.groups,
            totalPets: botData.pets
        })
    });
};
```

## 🛠️ Anpassungen

### Styling ändern
Bearbeite `public/style.css` für Design-Anpassungen:
- CSS-Variablen für Farben in `:root`
- Responsive Breakpoints in Media Queries
- Animationen und Transitions

### Funktionalität erweitern
Bearbeite `public/script.js` für neue Features:
- Neue API-Endpoints hinzufügen
- Zusätzliche Statistiken implementieren
- Custom Animationen erstellen

### API erweitern
Bearbeite `api/server.js` für Backend-Änderungen:
- Neue Endpoints hinzufügen
- Datenbank-Integration
- Authentifizierung implementieren

## 📞 Support

Bei Problemen:
1. Überprüfe die Vercel Deployment Logs
2. Teste die API-Endpoints direkt
3. Kontrolliere die Browser-Konsole für JavaScript-Fehler

## 🎯 Nächste Schritte

Nach erfolgreichem Deployment:
1. Custom Domain konfigurieren (optional)
2. Bot-Integration für Live-Daten einrichten
3. Analytics und Monitoring hinzufügen
4. SSL-Zertifikat überprüfen

---

**Hinweis**: Diese Dateien sind speziell für Vercel optimiert und verwenden andere Namen als die ursprünglichen Website-Dateien, um Konflikte zu vermeiden.