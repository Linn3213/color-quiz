# Färganalys Quiz - Linnartistry

En interaktiv färganalys-quiz som lead magnet för The Personal Glow Up Project.

## Snabbstart

### 1. Klona och installera
```bash
git clone [your-repo-url]
cd color-quiz-app
npm install
```

### 2. Lägg till din GHL Webhook URL
Skapa en fil `.env` i projektets rot:
```
REACT_APP_WEBHOOK_URL=https://services.leadconnectorhq.com/hooks/YOUR_WEBHOOK_ID
```

### 3. Starta lokalt
```bash
npm start
```

### 4. Publicera på Vercel
1. Pusha till GitHub
2. Gå till vercel.com
3. Importera ditt GitHub-repo
4. Lägg till miljövariabeln `REACT_APP_WEBHOOK_URL` i Vercel settings
5. Deploy!

## Data som skickas till GHL

När någon fyller i sin e-post skickas följande data:

```json
{
  "email": "kund@email.se",
  "color_season": "Light Spring",
  "color_season_id": "light-spring",
  "tags": "color-light-spring,quiz-completed",
  "best_colors": "Persika, ljus korall...",
  "tagline": "Ljus, varm och strålande som en vårmorgon",
  "timestamp": "2024-01-15T10:30:00.000Z",
  "source": "color-analysis-quiz"
}
```

## De 12 färgsäsongerna

| Säsong | ID |
|--------|-----|
| Light Spring | light-spring |
| Warm Spring | warm-spring |
| Clear Spring | clear-spring |
| Light Summer | light-summer |
| Soft Summer | soft-summer |
| Cool Summer | cool-summer |
| Soft Autumn | soft-autumn |
| Warm Autumn | warm-autumn |
| Deep Autumn | deep-autumn |
| Cool Winter | cool-winter |
| Clear Winter | clear-winter |
| Deep Winter | deep-winter |

## Bädda in på din sajt

### Via iframe
```html
<iframe 
  src="https://your-app.vercel.app" 
  width="100%" 
  height="800px" 
  frameborder="0"
></iframe>
```

### Via länk
Länka direkt till `https://your-app.vercel.app`

## GHL Automation Tips

Använd dessa tags för segmentering:
- `quiz-completed` - alla som genomfört quizzen
- `color-light-spring`, `color-warm-autumn`, etc. - specifik färgsäsong

Exempel på automation:
1. Trigger: Inbound Webhook
2. Action: Add Tag baserat på `color_season_id`
3. Action: Send Email med personaliserat resultat
4. Wait 2 days
5. Action: Send Email om The Personal Glow Up Project
