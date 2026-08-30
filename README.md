# Protesta e Nartës — React + Vite

Loja e njëjtë (Angry-Birds-style, tema e Lagunës së Nartës), tani si projekt i vërtetë
React, ndërtuar me [Vite](https://vitejs.dev) (që përdor Node.js si mjet ndërtimi/dev-server).

## Struktura

```
src/
  game/engine.js     -- gjithë logjika e lojës (fizika, vizatimi, hyrjet) — JS i pastër
  GameCanvas.jsx      -- komponenti React që mbështjell <canvas> dhe UI-në (pikët, radha, mesazhet)
  GameCanvas.css      -- stilet e UI-së mbi canvas
  App.jsx             -- rrënja e aplikacionit
  main.jsx            -- pika e hyrjes (ReactDOM.createRoot)
```

Fizika/vizatimi mbetet JS i pastër brenda `engine.js` (jo React state) sepse një lak
fizike në kohë reale duhet të lëvizë pozicionet çdo kornizë — ricaktimi i gjendjes së
React 60 herë/sekondë do ta ngadalësonte dhe komplikonte pa nevojë. React përdoret vetëm
për UI-në sipër canvas-it (pikët, niveli, radha e zogjve, mesazhet), të cilën motori i
lojës e njofton përmes një grupi "callbacks".

**Shënim për "Node":** këtu Node.js e ekzekuton vetëm serverin e zhvillimit (Vite) dhe
ndërtimin final — nuk ka backend/server API, sepse loja nuk ka nevojë të ruajë të dhëna
(s'ka leaderboard online, llogari, etj). Nëse do shtojmë një server real (p.sh. Express)
për rezultate të ruajtura online, mund ta shtoj lehtë më vonë.

## Si të nisësh

```bash
npm install
npm run dev
```

Hap adresën që shfaqet në terminal (zakonisht `http://localhost:5173`).

## Build për prodhim

```bash
npm run build
npm run preview   # për ta parë versionin e ndërtuar
```
