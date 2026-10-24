# HummerMDC-Architecture
Orquestador de infraestructura soberana, perimetral y de alta disponibilidad (HA) para el ecosistema Hummerfire.


![License](https://img.shields.io/badge/License-GPL--2.0-blue.svg)
![Proxmox](https://img.shields.io/badge/Proxmox-VE%209-E57000?logo=proxmox&logoColor=white)
![Talos](https://img.shields.io/badge/Talos-OS-FF7300?logo=linux&logoColor=white)
![Kubernetes](https://img.shields.io/badge/Kubernetes-K8s-326CE5?logo=kubernetes&logoColor=white)
![OPNsense](https://img.shields.io/badge/OPNsense-26.1.2%20HA-D94F00?logo=opnsense&logoColor=white)
![HomeAssistant](https://img.shields.io/badge/Home_Assistant-MCP-41BDF5?logo=home-assistant&logoColor=white)
![Status](https://img.shields.io/badge/Status-In_Progress-yellow)


# 🏗️ HummerMDC — Micro Data Center (V0.1)
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
