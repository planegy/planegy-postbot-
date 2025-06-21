# 📢 Planegy Postbot

Ein halbautomatisches LinkedIn-Posting-System für [Planegy.de](https://www.planegy.de) – mit KI-generiertem Content, Scheduler und Telegram-Benachrichtigung.  
Entwickelt für kommunale Wärmeplanung, ESG-Themen und dezentrale Energielösungen.

---

## 🧠 Was kann die App?

- Inhalte generieren mit GPT-4 (OpenAI)
- Manuell oder automatisch auf LinkedIn posten
- Auto-Post werktäglich um 08:30 Uhr (abschaltbar)
- Benachrichtigung via Telegram bei Auto-Posts
- Einfache Web-Oberfläche für Content-Steuerung

---

## 🚀 Deployment via Fly.io (empfohlen)

### Voraussetzungen

- GitHub-Konto mit diesem Repository
- [Fly.io Account](https://fly.io)
- API-Schlüssel von OpenAI, LinkedIn & Telegram

### Schritt 1: Repository bei Fly.io verbinden

1. Gehe zu [https://fly.io/apps](https://fly.io/apps)
2. Klicke auf **"Create App"**
3. Wähle dein GitHub-Repo `planegy-postbot`
4. Fly erkennt das `Dockerfile` automatisch

---

### Schritt 2: Secrets setzen

In Fly.io → deine App → „Secrets“ → folgende Einträge hinzufügen:

| Name | Beschreibung |
|------|--------------|
| `OPENAI_API_KEY` | Dein OpenAI Key (`sk-...`) |
| `LINKEDIN_ACCESS_TOKEN` | LinkedIn OAuth Token |
| `LINKEDIN_PERSON_URN` | z. B. `urn:li:person:xyz...` |
| `TELEGRAM_TOKEN` | Token vom Telegram-Bot |
| `TELEGRAM_CHAT_ID` | Deine Telegram-Chat-ID |

---

### Schritt 3: App starten

Nach dem ersten Deploy kannst du die Web-App direkt öffnen unter:  
`https://dein-app-name.fly.dev`

---

## ⚙️ Lokale Nutzung (optional)

```bash
git clone https://github.com/deinuser/planegy-postbot.git
cd planegy-postbot
cp .env.example .env
# Trage deine Schlüssel ein
pip install -r requirements.txt
python app.py
