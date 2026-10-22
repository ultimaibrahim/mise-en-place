<div align="center">
  <img src="./assets/banner.png" alt="mise en place Banner" width="100%" style="border-radius: 14px;" />
</div>

# ⚡ mise en place
### Enterprise Inventory, Supply Chain Ledger & Touch Picking Engine

[![Interface: Mobile Thumb Ergonomics](https://img.shields.io/badge/UX-Thumb%20Ergonomics-10b981.svg)](#)
[![Runtime: Apps Script V8 & Node](https://img.shields.io/badge/Runtime-GAS%20V8%20%7C%20Node.js-f59e0b.svg)](#)
[![Frontend: React + Vite](https://img.shields.io/badge/Frontend-React%2018%20%2B%20TypeScript-6366f1.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

*Motor distribuido de control de inventarios, conciliación inteligente de insumos (Fuzzy Matching con N-Grams) y terminales de picking táctil para operaciones de alta velocidad en cocinas y bodegas.*

---

## 🏗️ Arquitectura Hub-and-Spoke

```mermaid
flowchart TD
    subgraph UI ["Terminales Táctiles (Spokes)"]
        Kiosk["Terminal de Picking Bodega (1050x700px)"]
        StoreApp["Web App Móvil para Tiendas (React + Vite)"]
    end

    subgraph Engine ["Motor Central (Hub Ledger)"]
        Kardex["Mise Kardex Engine (GAS V8)"]
        Fuzzy["Conciliador N-Grams (Fuzzy Matching)"]
        Locking["Control de Concurrencia & Folios Únicos"]
    end

    subgraph Storage ["Persistencia & Sincronización"]
        Sheets["Google Sheets API v4 (_SYNC Ledger)"]
        Cache["Almacén Offline Local (IndexedDB / State)"]
    end

    UI --> Engine
    Engine --> Storage
```

---

## ⚡ Capacidades Principales

- **Conciliación Inteligente con N-Grams**: Resuelve discrepancias ortográficas, abreviaciones y nombres alternativos de insumos con tolerancia a variaciones de operadores en cocina.
- **Ergonomía Táctil en Zona del Pulgar**: Diseñado específicamente para pantallas táctiles de bodega y smartphones con una sola mano, eliminando scrolls innecesarios y garantizando objetivos táctiles superiores a 48px.
- **Control de Concurrencia de Folios**: Previene condiciones de carrera (*race conditions*) en transferencias simultáneas entre sucursales mediante bloqueos atómicos.
- **Motor Kardex de Doble Partida**: Registro inmutable de entradas, mermas, traspasos y consumos teóricos contra inventario físico.

---

## 📁 Estructura del Repositorio

- `engine-apps-script/`: Motor central de Kardex y diálogos de picking en Google Apps Script V8 desacoplados de identificadores privados.
- `web-app/`: Aplicación frontend en React + TypeScript y Vite con diseño modular y componentes de picking táctil.
- `identidad/`: Sistema de identidad corporativa, símbolos SVG monocromáticos y manual de diseño.

---

<div align="center">
  <sub>Diseñado y construido con obsesión por el detalle por <a href="https://ultimaibrahim.dev">Ibrahim García</a></sub>
</div>
