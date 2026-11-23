<img src="https://capsule-render.vercel.app/api?type=waving&color=0:0f2027,50:203a43,100:2c5364&height=180&section=header&text=Social%20Subtext%20Decoder&fontSize=42&fontColor=ffffff&fontAlignY=38&desc=Decode%20tone%20and%20implied%20meaning%20%C2%B7%20practise%20conversations%20with%20a%203D%20avatar&descAlignY=60&descSize=15" width="100%"/>

<div align="center">

<img src="https://skillicons.dev/icons?i=react,vite,tailwind,threejs,nodejs,express,postgres&theme=dark" />
<br/><br/>
<img src="https://img.shields.io/badge/LLM-Gemini%202.5%20Flash%20%2B%20GPT--4o--mini-4285F4?style=flat-square" />
<img src="https://img.shields.io/badge/Voice-ElevenLabs%20%2B%20Whisper-black?style=flat-square" />
<img src="https://img.shields.io/badge/Built%20at-Healthiathon-orange?style=flat-square" />

</div>

---

## 🧠 ᴏᴠᴇʀᴠɪᴇᴡ

Some messages say one thing and mean another. Social Subtext Decoder takes a message, explains its tone and implied meaning, and suggests replies that fit the context. It also lets people rehearse real conversations (a job interview, ordering at a restaurant, or a custom situation) with a talking 3D avatar.

It was built as a hackathon project at **Healthiathon**, aimed at communication-skills practice and accessibility.

---

## ✨ ꜰᴇᴀᴛᴜʀᴇꜱ

| Mode | What it does |
|:--|:--|
| 💬 **Decoder** | Paste a message and get its tone, the likely subtext, and suggested replies (Gemini 2.5 Flash) |
| 🗣️ **Practice** | Pick a situation and role-play it with an AI partner; sessions and messages are saved |
| 🎭 **Avatar practice** | A 3D avatar (Three.js) replies via GPT-4o-mini and speaks with lip-sync and facial expressions |
| 🎙️ **Live conversation** | Talk by voice: speech-to-text (Whisper) in, text-to-speech (ElevenLabs) out |
| 🏅 **Gamification** | XP, levels and an end-of-session summary |
| 📜 **History** | Review or delete past decodes |

---

## 🏗️ ᴀʀᴄʜɪᴛᴇᴄᴛᴜʀᴇ

```text
React + Vite + Tailwind ──REST / Socket.IO──► Express API ──► PostgreSQL
  ├─ Three.js avatar (lip-sync, expressions)        ├─ Gemini 2.5 Flash · GPT-4o-mini (avatar)
  └─ face-api.js, Web Speech                        ├─ ElevenLabs TTS · Whisper STT
                                                    └─ zod validation · helmet · rate limiting
```

| Endpoint | Purpose |
|:--|:--|
| `POST /api/decode` | Decode a message |
| `GET /api/practice/situations` · `POST /api/practice/session` · `POST /api/practice/message` · `POST /api/practice/end` | Practice sessions |
| `POST /api/avatar/tts` · `POST /api/avatar/stt` · `POST /api/avatar/live` | Voice and avatar |
| `GET /api/history` · `DELETE /api/history/:id` | History |

---

## 🚀 ʀᴜɴ ɪᴛ ʟᴏᴄᴀʟʟʏ

The app lives in `projects/social-subtext-decoder/social-subtext-decoder/`.

```bash
# Backend (http://localhost:3001)
cd projects/social-subtext-decoder/social-subtext-decoder/backend
npm install
# create .env with GEMINI_API_KEY, ELEVEN_LABS_API_KEY, OPENAI_API_KEY
# and either DB_HOST/DB_USER/DB_PASSWORD/DB_NAME or USE_MOCK_DB=true
npm start

# Frontend
cd ../frontend
npm install
npm run dev
```

Set `USE_MOCK_DB=true` to run without PostgreSQL. The schema is in `backend/database/schema.sql`.

---

<div align="center">

**Navyashree J** · BTech CSE (AI/ML), PES University

<a href="https://github.com/Navyashree04"><img src="https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white" /></a>
<a href="https://linkedin.com/in/navyashreej1"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" /></a>

</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:2c5364,50:203a43,100:0f2027&height=100&section=footer" width="100%"/>
