# MoveGreen
 
A web app that helps Boston commuters choose a lower-emission way to travel. You enter a start and end point, and MoveGreen compares the route across **8 transportation modes**, estimating travel time and **CO₂ emissions** for each. An **AI travel assistant** answers questions about your options.
 
> Built at **EcoHacks** as a team project.
> ## Features
 
- Compares driving, bus, tram, subway, biking, walking, e-bike, and e-scooter
- Traffic-aware routing that uses departure time (Google Maps Directions API)
- Per-mode carbon emission estimates (kg CO₂ per km)
- Gemini 2.5 Flash chat assistant that uses your route data as context, so you can ask things like "Which option saves the most emissions?"
- Interactive map view
## Tech stack
 
**Backend:** Node.js, Express, Axios
**APIs:** Google Maps (Directions and JavaScript), Google Gemini
**Frontend:** HTML, CSS, vanilla JavaScript
 
## Architecture
 
```
backend/
├── server.js        # Express API
│   ├── GET  /api/routes   → queries Google Maps for each mode and adds emissions estimates
│   └── POST /api/chat     → sends the question plus route context to Gemini
└── public/          # static frontend served by Express
```
 
API keys are loaded from environment variables and are never committed.
 
## Run locally
 
```bash
cd backend
cp .env.example .env    # add GOOGLE_API_KEY and GEMINI_API_KEY
npm install
node server.js
# open http://localhost:8080
```
 
## Team
 
- **Hiya Verma** ([@hiyaverms](https://github.com/hiyaverms))
- **Brady Xue** ([@BradyXue1](https://github.com/BradyXue1))
- **Linus Lindon** ([@PlatinumPawn](https://github.com/PlatinumPawn))
## Emissions factors
 
| Mode | kg CO₂ / km |
|---|---|
| Driving | 0.22 |
| Bus | 0.16 |
| Tram | 0.09 |
| Subway | 0.08 |
| E-scooter | 0.08 |
| E-bike | 0.01 |
| Biking / Walking | 0.00 |
 
