
![HummerMDC_banner](01_Documentacion/img/MDC_2.png)


![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)
![License: CC BY-SA 4.0](https://img.shields.io/badge/License-CC_BY--SA_4.0-lightgrey.svg?style=flat-square)
![Proxmox](https://img.shields.io/badge/Proxmox-VE_9-E57000?style=flat-square&logo=proxmox&logoColor=white)
![Talos](https://img.shields.io/badge/Talos-OS-FF7300?style=flat-square)
![Kubernetes](https://img.shields.io/badge/Kubernetes-K8s-326CE5?style=flat-square&logo=kubernetes&logoColor=white)
![Odoo](https://img.shields.io/badge/Odoo-ERP-714B67?style=flat-square&logo=odoo&logoColor=white)
![Debian](https://img.shields.io/badge/Debian-12-A81D33?style=flat-square&logo=debian&logoColor=white)
![OPNsense](https://img.shields.io/badge/OPNsense-26.1.2_HA-D94F05?style=flat-square)
![Status](https://img.shields.io/badge/Status-In_Progress-yellow?style=flat-square)


---



# 🏗️ HummerMDC — Micro Data Center (V0.1)

> Infraestructura self-hosted de Alta Disponibilidad (HA) para IA (RAG/MCP), Domótica y Sistemas Críticos Empresariales (Odoo ERP). Orquestación bare-metal con cero dependencias cloud y control absoluto de datos.

---
Bienvenido al repositorio oficial del **HummerMDC**, el Micro Data Center (MDC) de producción de **Hummerfire SpA**. 

Este no es un *Homelab*. Es una infraestructura crítica diseñada bajo los principios de **Economía de Guerra** (cero dependencia de la nube, hardware reciclado de alto rendimiento y soberanía absoluta de los datos) para sostener el ecosistema de **Spareware SpA** y futuras expansiones (BoxSpare, SpareTrack, Humanimals).

## 🏛️ El Ecosistema
*   **Spareware SpA (Retail):** El núcleo operativo. Venta de repuestos automotrices.
*   **Hummerfire SpA (Holding):** Dueño de la Propiedad Intelectual, la infraestructura y los datos.
*   **HummerMDC (Infraestructura):** El motor tecnológico que hace funcionar el ERP (Odoo), la IA local y los servicios en la nube.

## ⚙️ Stack Tecnológico Principal
El diseño de la V0.1 prioriza la Alta Disponibilidad (HA) donde genera ingresos, y la eficiencia extrema donde no.

*   **Virtualización:** Proxmox VE (3 Nodos Baremetal).
*   **Cloud-Native / K8s:** Talos OS administrado con Sidero Omni (3 Nodos Baremetal).
*   **ERP:** Odoo (Stateless) + Nginx (Longpolling).
*   **Base de Datos:** PostgreSQL + Patroni (HA) + PgBouncer + TimescaleDB + PgVector.
*   **Caché / Sesiones:** Valkey + Sentinel.
*   **Almacenamiento:** TrueNAS (NFS) + MinIO (S3 distribuido).
*   **Red y Balanceo:** OPNsense (CARP) + HAProxy + Keepalived + Wireguard.
*   **Observabilidad:** Prometheus, Grafana, Loki, OpenTelemetry.

## 🗺️ Topología del Sistema
