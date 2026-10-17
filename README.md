# ShopyBuzz AI backend

Files: server.js, package.json, products.json (no npm packages needed).

## Render par deploy (Web Service)
1. GitHub par naya repository banao: shopybuzz-api. In files ko upload karo.
2. Render: New + > Web Service > ye repository chuno.
3. Runtime: Node. Build Command: khaali ya npm install. Start Command: node server.js
4. Environment Variables:
   - AI_API_KEY  = tumhari AI company ki API key (kabhi GitHub par mat daalna)
   - PROVIDER    = anthropic (ya openai ya gemini)
   - MODEL       = anthropic ke liye optional; openai/gemini ke liye zaroori (company ki site par current model naam dekho)
   - ORIGINS     = https://shopybuzz.in,https://www.shopybuzz.in,https://shopybuzz.onrender.com
   - DAILY_LIMIT = 40 (har IP ke liye roz ke messages)
5. Deploy ke baad .../api/health kholo: ready true dikhna chahiye.
6. Wahi link config.js mein daalo: window.SB_API = "https://....onrender.com";

## Affiliate links
products.json mein har product ke "link" mein apna affiliate link paste karo.
Khaali link wale product par "kharido" abhi link nahi kholega.
