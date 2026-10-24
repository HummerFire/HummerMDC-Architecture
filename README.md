
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
Bienvenido a **HummerMDC**, el Micro Data Center (MDC) de producción de **Hummerfire SpA**. 

Este proyecto nacio como un [*Homelab*](https://github.com/HummerFire/HummerLab-Infrastructure), evolucionando como respuesta a las necesidades de desarrollo empresarial. Infraestructura crítica diseñada bajo los principios de **Filosofía OUTLIER** (cero dependencia de la nube, hardware declarado obsoleto pero de alto rendimiento y soberanía absoluta de los datos) para sostener el ecosistema de **Spareware SpA** y futuras expansiones.

---

## 🏛️ El Ecosistema

### I. **Hummerfire SpA (Holding):** Startup Matriz encargada de las decisiones estratégicas globales.
* **HummerMDC (Infraestructura):** El motor tecnológico que servicios selfhosted y cloud para sus filiales.
### II. **Spareware SpA (Retail):** PYME filial encargada del retail. 



---

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

---

## 🗺️ Topología del Sistema

### Mapa Físico (Baremetal)
```mermaid
graph TD
    ISP((ISP Router<br/>WAN: 192.168.100.1))
    
    subgraph Red_Perimetro [Perímetro y Firewalls]
        H00[OPNsense H00<br/>Master CARP]
        H01[OPNsense H01<br/>Backup CARP]
    end

    Switch_Tonto{{Switch No Administrable}}

    subgraph Servidores_Fisicos [Servidores Baremetal N01 al N06]
        NIC1[NIC 1: LAN / Gestión<br/>10.0.1.0/24]
        NIC2[NIC 2: Datos / Storage<br/>192.168.10.0/24]
        BMC[NIC 3: IPMI / BMC<br/>10.99.0.0/24]
    end

    ISP --> H00
    ISP --> H01
    H00 <-->|Cable Crossover pfSync| H01
    H00 --> Switch_Tonto
    H01 --> Switch_Tonto
    NIC1 --> Switch_Tonto
    NIC2 --> Switch_Tonto
    BMC --> Switch_Tonto
```

