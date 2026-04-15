<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=200&section=header&text=Marcos%20Paes&fontSize=52&fontColor=fff&animation=twinkling&fontAlignY=38&desc=Desenvolvedor%20Full%20Stack%20%C2%B7%20Visao%20Computacional%20%C2%B7%20IoT&descAlignY=58&descSize=17" width="100%" />

<p align="center">
  <img src="https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=18&duration=2800&pause=700&color=42F7F3&center=true&vCenter=true&width=720&lines=Estudante+de+SI+e+pesquisador+no+LEDS+Cachoeiro;Pipeline+de+visao+computacional+com+SAM3+%2B+Hugin+%2B+OpenCV;APIs+assincronas%3A+FastAPI+%2B+MQTT+%2B+WebSocket+%2B+Docker;Do+protocolo+serial+binario+ate+segmentacao+com+IA" alt="Typing SVG" />
</p>

<p align="center">
  <a href="mailto:marcosampaes@gmail.com">
    <img src="https://img.shields.io/badge/Gmail-marcosampaes%40gmail.com-EA4335?style=flat-square&logo=gmail&logoColor=white" />
  </a>
  &nbsp;
  <a href="https://linkedin.com/in/marcosampaes">
    <img src="https://img.shields.io/badge/LinkedIn-Marcos_Paes-0A66C2?style=flat-square&logo=linkedin&logoColor=white" />
  </a>
  &nbsp;
  <img src="https://komarev.com/ghpvc/?username=MarcosAMPaes&style=flat-square&color=42F7F3&label=Visitas" />
</p>

---

<img align="right" width="340" src="https://media.giphy.com/media/qgQUggAC3Pfv687qPC/giphy.gif" alt="coding gif" />

## Quem sou eu

Estudo **Sistemas de Informação** e atuo como pesquisador no **LEDS Cachoeiro**, onde converto problemas reais de indústria e produção em sistemas funcionais e bem arquitetados.

Meu trabalho transita entre camadas: do protocolo serial binário de encoders industriais até pipelines de segmentação com IA de última geração rodando completamente no edge — sem depender de nuvem.

&nbsp;&nbsp;&nbsp;🏭 &nbsp;Automatizei estúdio fotográfico profissional com pipeline end-to-end de IA  
&nbsp;&nbsp;&nbsp;🤖 &nbsp;Implementei **Meta SAM3** em segmentação por prompt textual em produção real  
&nbsp;&nbsp;&nbsp;🔌 &nbsp;Construí leitor de protocolo serial binário com máquina de estados industrial  
&nbsp;&nbsp;&nbsp;🛒 &nbsp;Desenvolvi e-commerce completo com PIX, OAuth Google e CI/CD com Jenkins  
&nbsp;&nbsp;&nbsp;📡 &nbsp;Projetei sistemas distribuídos com MQTT, WebSocket e dashboards em tempo real  
&nbsp;&nbsp;&nbsp;🎓 &nbsp;Entreguei sistema para o **IFES**: controle de presença com QR Code em produção  

<br clear="right"/>

---

## Projetos em Destaque

### Pipeline de Estúdio Fotográfico — LEDS Cachoeiro

> Sistema modular **100% edge** para automação de captura panorâmica profissional com 3 câmeras.
> Um único disparo — HTTP ou CLI — executa o fluxo completo da captura ao artefato segmentado.

```
Encoder Rotativo (serial binário 10 bytes)
  └─ Máquina de estados → detecção de objeto → compensação de latência por velocidade
           │
           ▼
3× Câmeras USB (UVC) → captura simultânea → Calibração geométrica (OpenCV, mapas .npz)
           │
           ▼
  Stitching panorâmico (Hugin: pto_gen → cpfind → enblend) → panorama_final.jpg
           │
           ▼
  Segmentação por prompt textual (Meta SAM3 + PyTorch) → máscara · crop · overlay
           │
           ▼
  Upload S3-compatível (AWS · MinIO · Backblaze B2) + SQLite para retomada de jobs
```

<details>
<summary><b>Ver módulos do pipeline</b></summary>

<br/>

| Módulo | Stack | Responsabilidade |
|--------|-------|-----------------|
| **studio-encoder** | Python · pyserial · FastAPI · FSM | Parsing de protocolo binário (10 bytes/frame), ressincronização automática, máquina de estados de lifecycle de objeto, cálculo de lead time por velocidade |
| **studio-orchestrator** | FastAPI · OpenCV · PyTorch · SQLite · boto3 | Coordena todos os estágios como subprocessos com PYTHONPATH isolation (SAM3 requer Python 3.10, orquestrador usa 3.12) |
| **studio-stitching** | Python · Pillow · Hugin | Composição panorâmica de 3 imagens pré-calibradas com contrato de resolução exato: 1440×1080 px |
| **studio-segmentacao** | PyTorch · SAM3 · NumPy | Wrapper de segmentação com commit SHA pinado, fallback para HuggingFace, artefatos: máscara, RGBA, crop, overlay + JSON |
| **studio-calibracao** | Python · OpenCV | Calibração geométrica individual por câmera, gera mapas de undistortion (.npz) |
| **central_commander** | FastAPI · React 18 · TypeScript · aiomqtt · WebSocket | Dashboard em tempo real: câmeras, encoders, telemetria (CPU/RAM/disco), controle de spotlights via GPIO |

</details>

---

### VVN — Plataforma de E-commerce

> API REST completa para e-commerce com arquitetura em camadas, integrações reais de pagamento e pipeline CI/CD.

**Arquitetura:** `Routes → Services → Repositories → SQL Layer → MySQL 8` — sem ORM, SQL manual com JOINs e transactions  
**Padrões aplicados:** Repository Pattern · DTO Pattern · Service Layer · RBAC · Webhook assíncrono (Mercado Pago)

<p>
  <img src="https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white" />
  <img src="https://img.shields.io/badge/MySQL_8-4479A1?style=flat-square&logo=mysql&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-2496ED?style=flat-square&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/Jenkins_CI%2FCD-D24939?style=flat-square&logo=jenkins&logoColor=white" />
  <img src="https://img.shields.io/badge/JWT-000000?style=flat-square&logo=jsonwebtokens&logoColor=white" />
  <img src="https://img.shields.io/badge/Google_OAuth-4285F4?style=flat-square&logo=google&logoColor=white" />
  <img src="https://img.shields.io/badge/Mercado_Pago-PIX-00BCCA?style=flat-square" />
</p>

Cobre o ciclo completo: catálogo com variações e estoque, carrinho persistente, cálculo de frete (Melhor Envio), pagamento PIX com webhook, gestão de pedidos, painel administrativo com analytics, campanhas promocionais e cupons com desconto em múltiplos níveis.

---

### QRCheck — Controle de Presença por QR Code

> Sistema de gerenciamento de eventos e check-in desenvolvido para o **IFES** (Instituto Federal do Espírito Santo).

**Stack:** `FastAPI · SQLite · Jinja2 · html5-qrcode · qrcode + Pillow · bcrypt`  
**Destaques técnicos:** Scanner de câmera em tempo real no navegador · cookies HTTP-only · validação de CPF com dígito verificador · exportação de presença em CSV via streaming · constraint `UNIQUE(evento, participante)` a nível de banco

---

### Esteira — Pipeline Embarcado de Inspeção Visual

> Sistema de visão computacional embarcado para linha de produção industrial em Raspberry Pi.

**Stack:** `Python · picamera2 · OpenCV · paho-mqtt · NumPy · psutil`  
**Destaques técnicos:** Dual-camera (OV5647 preview + IMX477 principal) · controlador proporcional (P-controller) de exposição com ROI central · fail-safe de superexposição por análise de histograma · transmissão MQTT QoS 1 com ACK · suite de stress-test com relatório HTML automático (latência P50/P95/P99)

---

## Stack Tecnológico

### Linguagens
<p>
  <img src="https://skillicons.dev/icons?i=python,typescript,javascript,html,css" />
</p>

### Web & Backend
<p>
  <img src="https://skillicons.dev/icons?i=fastapi,react,vite,nodejs,nginx,tailwind" />
</p>

### Dados, DevOps & Infra
<p>
  <img src="https://skillicons.dev/icons?i=mysql,sqlite,docker,linux,git,aws" />
</p>
<p>
  <img src="https://img.shields.io/badge/Jenkins-CI%2FCD-D24939?style=flat-square&logo=jenkins&logoColor=white" />
  <img src="https://img.shields.io/badge/WebSocket-Tempo_Real-2E86AB?style=flat-square" />
  <img src="https://img.shields.io/badge/MQTT-aiomqtt%20%7C%20paho-660066?style=flat-square&logo=eclipsemosquitto&logoColor=white" />
</p>

### Visão Computacional & Machine Learning
<p>
  <img src="https://skillicons.dev/icons?i=pytorch,opencv" />
  <img src="https://img.shields.io/badge/Meta_SAM3-Segment_Anything-0866FF?style=flat-square&logo=meta&logoColor=white" />
  <img src="https://img.shields.io/badge/Hugin-Panorama_Stitching-FF6600?style=flat-square" />
  <img src="https://img.shields.io/badge/NumPy-013243?style=flat-square&logo=numpy&logoColor=white" />
  <img src="https://img.shields.io/badge/Pillow-PIL-3776AB?style=flat-square&logo=python&logoColor=white" />
</p>

### Sistemas Embarcados & IoT
<p>
  <img src="https://skillicons.dev/icons?i=raspberrypi" />
  <img src="https://img.shields.io/badge/pyserial-Protocolo_Serial_Binario-2E86AB?style=flat-square" />
  <img src="https://img.shields.io/badge/picamera2-IMX477_%7C_OV5647-A22846?style=flat-square&logo=raspberrypi&logoColor=white" />
  <img src="https://img.shields.io/badge/gpiod-GPIO_Linux-6A994E?style=flat-square" />
  <img src="https://img.shields.io/badge/UVC-V4L2-0078D7?style=flat-square" />
</p>

---

## Estatísticas

<div align="center">
  <img height="165em" src="https://github-readme-stats.vercel.app/api?username=MarcosAMPaes&show_icons=true&theme=dracula&include_all_commits=true&count_private=true&hide_border=true" />
  <img height="165em" src="https://github-readme-stats.vercel.app/api/top-langs/?username=MarcosAMPaes&layout=compact&langs_count=8&theme=dracula&hide_border=true" />
</div>

<div align="center">
  <img src="https://streak-stats.demolab.com?user=MarcosAMPaes&theme=dracula&hide_border=true&date_format=j%20M%5B%20Y%5D" alt="GitHub Streak" />
</div>

---

## A cobrinha comendo meus commits

<div align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/MarcosAMPaes/MarcosAMPaes/output/github-contribution-grid-snake-dark.svg" />
    <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/MarcosAMPaes/MarcosAMPaes/output/github-contribution-grid-snake.svg" />
    <img alt="snake animation" src="https://raw.githubusercontent.com/MarcosAMPaes/MarcosAMPaes/output/github-contribution-grid-snake.svg" />
  </picture>
</div>

---

<img src="https://capsule-render.vercel.app/api?type=waving&color=gradient&customColorList=6,11,20&height=100&section=footer" width="100%" />
