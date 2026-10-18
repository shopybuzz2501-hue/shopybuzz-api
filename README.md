[README-1.md](https://github.com/user-attachments/files/33638262/README-1.md)
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

## Gmail OTP login (naye environment variables)
Render ke Web Service mein ye add karo:
- AUTH_SECRET   = lamba random text (kam se kam 32 akshar), kisi ko mat batana. Badalne par sab log logout ho jayenge.
- EMAIL_PROVIDER = resend (ya brevo)
- EMAIL_API_KEY  = email service ki API key
- EMAIL_FROM     = ShopyBuzz <login@shopybuzz.in>   (wo domain email service mein verify hona chahiye)
- EMAIL_DOMAINS  = gmail.com   (sab email chalane ho to: *)
- DAILY_LIMIT_USER = 80 (logged-in user ke roz ke AI messages, optional)

Check: /api/health kholo, "auth": true dikhna chahiye.
Dhyan: EMAIL_PROVIDER=mock sirf testing ke liye hai (OTP server log mein dikhta hai), live par kabhi mat rakhna.
