# Spotter AI — Weather-Aware Truck Routing

> A modern, production-grade truck routing platform that evaluates weather conditions at estimated arrival times along real road corridors, calculates dynamic cargo-wind risks, and recommends the safest route.

**Developed by [Numan Asghar](https://portfolio-numanasghar.vercel.app/)** • [GitHub Repository](https://github.com/NumanAsghar901/Spotter-AI-Weather-Routing-App)

---

## ✨ Key Features

- **🚛 Intelligent Truck Routing**: Multi-alternative highway routes calculated with TomTom Truck Routing API following real vehicle height, weight, and dimension parameters.
- **🌦️ ETA-Synchronized Forecasts**: Checkpoint weather forecasts queried from Open-Meteo for the exact estimated arrival time at each segment.
- **⚠️ Dynamic Cargo-Aware Risk Engine**: Automatic wind, rain, and snow risk classification factored with vehicle empty tare + cargo weight.
- **🗺️ Interactive Map & Radar Corridor**: MapLibre GL visualization with clickable checkpoints, color-coded risk segments, and a 0–48 hour weather forecast slider.
- **🎨 Premium Golden UI/UX**: Sleek dark and light themes with glowing gold accents, fully responsive across mobile, tablet, and desktop.

---

## 🛠️ Tech Stack

- **Frontend**: React 19, TypeScript, Vite, Tailwind CSS 4, MapLibre GL JS, Lucide Icons.
- **Backend**: Python 3.13, Django 5.2 LTS, Django REST Framework, Requests, Redis.
- **APIs**: TomTom (Routing & Geocoding), Open-Meteo (Hourly Weather), CARTO Positron (Basemaps).
- **Deployment**: Vercel Services (monorepo frontend + serverless Django WSGI).

---

## 🚀 Quick Start (Local Development)

### 1. Backend Setup
```powershell
# Create and activate virtual environment
python -m venv .venv
.\.venv\Scripts\Activate.ps1

# Install dependencies
pip install -r backend\requirements.txt

# Configure environment variables
Copy-Item backend\.env.example backend\.env
# Edit backend/.env and insert your TOMTOM_API_KEY

# Start Django development server (runs on port 8000)
python backend\manage.py runserver 127.0.0.1:8000
```

### 2. Frontend Setup
```powershell
# In a separate terminal
cd frontend
npm install
npm run dev
```
Open **[http://localhost:5173](http://localhost:5173)** in your browser.

---

## 🌐 Deploy to Vercel

1. Import this repository into [Vercel](https://vercel.com/new).
2. Set the following **Environment Variables** in project settings:
   - `TOMTOM_API_KEY`: Your TomTom developer key.
   - `REDIS_URL`: Upstash/Vercel Redis TLS connection URL (`rediss://...`).
   - `SECRET_KEY`: Random 64-character Django secret (`python -c "import secrets; print(secrets.token_urlsafe(64))"`).
   - `DJANGO_DEBUG`: `false`
3. Click **Deploy**. Both the Vite frontend and Django WSGI backend deploy seamlessly under one domain via [vercel.json](vercel.json).

---

## 🧪 Testing

```powershell
# Run backend tests (70 unit & integration tests)
python backend\manage.py test backend/tests

# Run frontend tests & build check
npm --prefix frontend test
npm --prefix frontend run build
```

---

## 📄 Author

Developed with care by **[Numan Asghar](https://portfolio-numanasghar.vercel.app/)**.
