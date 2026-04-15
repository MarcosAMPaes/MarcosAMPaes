<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=180&section=header&text=Marcos%20Paes&fontSize=50&fontColor=fff&animation=twinkling&fontAlignY=36&desc=LAIR%20%E2%80%A2%20Incubadora%20IFES%20Cachoeiro%20%7C%20wisestonetech&descAlignY=56&descSize=15" width="100%" />

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=16&duration=2600&pause=800&color=42F7F3&center=true&vCenter=true&width=680&lines=Visao+Computacional+%2B+ML+%2B+IoT+%2B+Full+Stack;Pipeline+edge%3A+SAM3+%2B+OpenCV+%2B+Hugin+%2B+MQTT;FastAPI+%2B+React+%2B+TypeScript+%2B+Docker+%2B+Jenkins;Sistemas+que+saem+do+papel+e+vao+pra+producao" />
</p>

<p align="center">
  <a href="mailto:marcosampaes@gmail.com"><img src="https://img.shields.io/badge/Gmail-EA4335?style=flat-square&logo=gmail&logoColor=white" /></a>
  <a href="https://www.linkedin.com/in/marcos-ant%C3%B4nio-mendes-paes-0ba4162ba/"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=linkedin&logoColor=white" /></a>
  <img src="https://komarev.com/ghpvc/?username=MarcosAMPaes&style=flat-square&color=42F7F3&label=visits" />
</p>

---

<img align="right" width="320" src="https://media.giphy.com/media/qgQUggAC3Pfv687qPC/giphy.gif" />

Estudante de **Sistemas de Informação**, pesquisador no **LAIR** da Incubadora IFES Cachoeiro e dev na **wisestonetech**. Sempre admirei muito quem trabalhava com tecnologia — acho nobre e bonito — e foi isso que me trouxe pra cá.

Fora do teclado, pratico jiu-jitsu e jogo. Levo pro código a mesma mentalidade do tatame: não aceito ficar travado. Se não sei, aprendo. Se não funciona de um jeito, tento de outro — até funcionar.

Sou bem aberto a novas conexões, adoro trabalhar em equipe e acredito que código bom nasce de conversa boa. Se quiser trocar ideia, tô por aqui.

<br clear="right"/>

---

## Projetos

### 🔬 Pipeline de Estúdio Fotográfico · wisestonetech + LAIR

Sistema modular para automação de captura panorâmica profissional com 3 câmeras. Tudo no edge, sem nuvem.

```
Encoder serial (10 bytes) → FSM + lead-time calc → 3× câmeras USB
→ Calibração (OpenCV .npz) → Stitching (Hugin) → Segmentação (SAM3) → S3
```

<details>
<summary>Módulos</summary>
<br/>

| | Stack | O que faz |
|--|-------|-----------|
| **studio-encoder** | pyserial · FastAPI · FSM | Protocolo binário, ressincronização automática, detecção de objetos com compensação de latência por velocidade |
| **studio-orchestrator** | FastAPI · OpenCV · PyTorch · SQLite · boto3 | Orquestra os estágios; isola ambientes Python incompatíveis (SAM3 usa 3.10, orchestrator usa 3.12) |
| **studio-stitching** | Pillow · Hugin | Composição panorâmica das 3 imagens calibradas |
| **studio-segmentacao** | PyTorch · SAM3 · NumPy | Segmentação por prompt textual; commit SHA pinado para reprodutibilidade |
| **studio-calibracao** | OpenCV | Gera mapas de undistortion (.npz) por câmera |
| **central_commander** | FastAPI · React 18 · TypeScript · aiomqtt | Dashboard de monitoramento: câmeras, encoders, telemetria, GPIO |

</details>

---

### 🛒 VVN — E-commerce · wisestonetech

API REST para e-commerce completo. Arquitetura em camadas sem ORM (Raw SQL), com integrações reais de pagamento e CI/CD.

`FastAPI` `MySQL 8` `Docker` `Jenkins` `JWT` `Google OAuth` `Mercado Pago PIX` `Melhor Envio`

> Padrões: Repository · Service Layer · DTO · RBAC · Webhook assíncrono

---

### 🌐 Projetos Web · LAIR + IFES

**central_commander** — Dashboard full stack com React 18 + TypeScript, TanStack Query, shadcn/ui, Tailwind CSS e Recharts. WebSocket para atualizações em tempo real; MQTT para comunicação com dispositivos. Build multi-stage Docker com Nginx.

**QRCheck** — Sistema de controle de presença por QR Code para eventos do IFES. Backend FastAPI com Jinja2 server-side; scanner de câmera em tempo real via `html5-qrcode`; cookies HTTP-only; exportação CSV via streaming.

---

### 🏭 Esteira — Inspeção Visual Embarcada · LAIR

Pipeline de visão computacional em Raspberry Pi para linha de produção industrial.

`picamera2` `OpenCV` `paho-mqtt` — Dual-camera (OV5647 + IMX477), P-controller de exposição por histograma ROI, fail-safe de superexposição, transmissão MQTT QoS 1 com ACK.

---

## Stack

**Linguagens**
<p><img src="https://skillicons.dev/icons?i=python,typescript,javascript,html,css" /></p>

**Web & Backend**
<p><img src="https://skillicons.dev/icons?i=fastapi,react,vite,tailwind,nodejs,nginx" /></p>

**Dados & DevOps**
<p><img src="https://skillicons.dev/icons?i=mysql,sqlite,docker,linux,git,aws" /></p>
<p>
  <img src="https://img.shields.io/badge/Jenkins-D24939?style=flat-square&logo=jenkins&logoColor=white" />
  <img src="https://img.shields.io/badge/MQTT-660066?style=flat-square&logo=eclipsemosquitto&logoColor=white" />
  <img src="https://img.shields.io/badge/WebSocket-2E86AB?style=flat-square" />
</p>

**Visão Computacional & ML**
<p>
  <img src="https://skillicons.dev/icons?i=pytorch,opencv" />
  <img src="https://img.shields.io/badge/SAM3-Meta_AI-0866FF?style=flat-square&logo=meta&logoColor=white" />
  <img src="https://img.shields.io/badge/Hugin-FF6600?style=flat-square" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white" />
</p>

**Embarcado & IoT**
<p>
  <img src="https://skillicons.dev/icons?i=raspberrypi" />
  <img src="https://img.shields.io/badge/pyserial-2E86AB?style=flat-square" />
  <img src="https://img.shields.io/badge/picamera2-A22846?style=flat-square&logo=raspberrypi&logoColor=white" />
  <img src="https://img.shields.io/badge/gpiod-6A994E?style=flat-square" />
</p>

---

## Stats

<div align="center">
  <img height="160em" src="https://github-readme-stats.vercel.app/api?username=MarcosAMPaes&show_icons=true&theme=dracula&hide_border=true&count_private=true" />
  <img height="160em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=MarcosAMPaes&layout=compact&langs_count=8&theme=dracula&hide_border=true" />
</div>
<div align="center">
  <img src="https://streak-stats.demolab.com?user=MarcosAMPaes&theme=dracula&hide_border=true" />
</div>

---

## Commits

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/MarcosAMPaes/MarcosAMPaes/output/github-contribution-grid-snake-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/MarcosAMPaes/MarcosAMPaes/output/github-contribution-grid-snake.svg" />
    <img alt="snake" src="https://raw.githubusercontent.com/MarcosAMPaes/MarcosAMPaes/output/github-contribution-grid-snake.svg" />
  </picture>
</div>

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer" width="100%" />