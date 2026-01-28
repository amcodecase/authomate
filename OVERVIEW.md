# Authomate - Technical Overview

![PHP](https://img.shields.io/badge/PHP-8.x-777BB4?logo=php&logoColor=white)
![Laravel](https://img.shields.io/badge/Laravel-API_First-FF2D20?logo=laravel&logoColor=white)
![License](https://img.shields.io/badge/License-Personal-lightgrey)

> **Authomate** is my personal system for backend development. It's designed to stop me from repeating the same patterns across projects and to help me focus on building real functionality.

---

## Project Structure

```
authomate/
├── ABOUTME.md              # About the author
├── README.md               # Project introduction
├── OVERVIEW.md             # Technical overview (this file)
└── packages/
    └── api/
        ├── v1/             # API version 1
        │   ├── Auth/
        │   ├── Users/
        │   └── Roles/
        ├── v2/             # API version 2
        │   ├── Auth/
        │   ├── Users/
        │   └── Permissions/
        └── v3/             # API version 3
            ├── Auth/
            ├── Teams/
            └── Billing/
```

---

## Package Architecture (Authomate Source)

```mermaid
graph TD
    A[Authomate] --> B[packages]
    B --> C[api]
    C --> V1[v1]
    C --> V2[v2]
    C --> V3[v3]
    
    V1 --> V1A[Auth]
    V1 --> V1B[Users]
    V1 --> V1C[Roles]
    
    V2 --> V2A[Auth]
    V2 --> V2B[Users]
    V2 --> V2C[Permissions]
    
    V3 --> V3A[Auth]
    V3 --> V3B[Teams]
    V3 --> V3C[Billing]
    
    style A fill:#FF2D20,stroke:#333,stroke-width:2px,color:#fff
    style B fill:#777BB4,stroke:#333,stroke-width:2px,color:#fff
    style C fill:#4FC08D,stroke:#333,stroke-width:2px,color:#fff
    style V1 fill:#3498db,stroke:#333,stroke-width:2px,color:#fff
    style V2 fill:#3498db,stroke:#333,stroke-width:2px,color:#fff
    style V3 fill:#3498db,stroke:#333,stroke-width:2px,color:#fff
```

---

## Laravel Project Integration (Destination)

> When you want to use a package, download it from Authomate and place it in your Laravel project's controllers:

```mermaid
graph TD
    subgraph Authomate["Authomate (Source)"]
        AP[packages/api/v1/Auth]
        UP[packages/api/v1/Users]
    end
    
    subgraph Laravel["Your Laravel Project (Destination)"]
        L[YourProject] --> App[app]
        App --> Http[Http]
        Http --> Controllers[Controllers]
        Controllers --> LV1[v1]
        Controllers --> LV2[v2]
        
        LV1 --> LA[Auth]
        LV1 --> LU[Users]
        LV1 --> LR[Roles]
        
        LV2 --> LA2[Auth]
        LV2 --> LU2[Users]
        LV2 --> LP2[Permissions]
    end
    
    AP -.->|copy| LA
    UP -.->|copy| LU
    
    style Authomate fill:#1a1a2e,stroke:#FF2D20,stroke-width:2px
    style Laravel fill:#1a1a2e,stroke:#4FC08D,stroke-width:2px
    style AP fill:#FF2D20,stroke:#333,stroke-width:1px,color:#fff
    style UP fill:#FF2D20,stroke:#333,stroke-width:1px,color:#fff
    style LA fill:#4FC08D,stroke:#333,stroke-width:1px,color:#fff
    style LU fill:#4FC08D,stroke:#333,stroke-width:1px,color:#fff
```

**Example path mapping:**
| Authomate Package | Laravel Destination |
|-------------------|---------------------|
| `packages/api/v1/Auth` | `app/Http/Controllers/v1/Auth` |
| `packages/api/v1/Users` | `app/Http/Controllers/v1/Users` |
| `packages/api/v2/Permissions` | `app/Http/Controllers/v2/Permissions` |

---

## What Authomate Does

| Feature | Description |
|---------|-------------|
| ![Reusable](https://img.shields.io/badge/-Reusable_APIs-0d1117?style=flat-square) | Backend building blocks I always implement |
| ![Assembly](https://img.shields.io/badge/-Quick_Assembly-0d1117?style=flat-square) | Assemble functionality without rewriting code |
| ![Fast](https://img.shields.io/badge/-Fast_&_Consistent-0d1117?style=flat-square) | Keeps development speedy while avoiding repetition |

---

## How I Use It

- Start a new project and include only what I need
- Everything follows consistent standards
- Fix a pattern once, use it everywhere

---

## Development Philosophy

| Principle | Meaning |
|-----------|----------|
| ![Minimal](https://img.shields.io/badge/-Minimalistic-blue?style=flat-square) | Only what I actually need |
| ![API](https://img.shields.io/badge/-API_First-red?style=flat-square) | Designed for JSON APIs |
| ![Modular](https://img.shields.io/badge/-Modular-green?style=flat-square) | Each piece works independently |
| ![Personal](https://img.shields.io/badge/-Personal-purple?style=flat-square) | Built for me and my workflow |

---

## Development Environment

> The environment I used to build Authomate:

### Host System

![Windows](https://img.shields.io/badge/Windows-Host_OS-0078D6?style=for-the-badge&logo=windows&logoColor=white)
![WSL](https://img.shields.io/badge/WSL-Linux_Subsystem-FCC624?style=for-the-badge&logo=linux&logoColor=black)

### Terminal & Shell

![Oh My Zsh](https://img.shields.io/badge/Oh_My_Zsh-Shell-4EAA25?style=flat-square&logo=gnu-bash&logoColor=white)
![Zellij](https://img.shields.io/badge/Zellij-Terminal_Multiplexer-FF6B6B?style=flat-square)

### Version Control

![Git](https://img.shields.io/badge/Git-Version_Control-F05032?style=flat-square&logo=git&logoColor=white)

### Databases & Caching

![PostgreSQL](https://img.shields.io/badge/PostgreSQL-Database-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Redis](https://img.shields.io/badge/Redis-Cache-DC382D?style=flat-square&logo=redis&logoColor=white)

### Containers & Monitoring

![Docker](https://img.shields.io/badge/Docker-Containers-2496ED?style=flat-square&logo=docker&logoColor=white)
![Netdata](https://img.shields.io/badge/Netdata-Monitoring-00AB44?style=flat-square&logo=netdata&logoColor=white)

### API Testing

![Postman](https://img.shields.io/badge/Postman-API_Testing-FF6C37?style=flat-square&logo=postman&logoColor=white)

> **Postman** is essential for testing all Authomate APIs during development.

### Browser

![Brave](https://img.shields.io/badge/Brave-Browser-FB542B?style=flat-square&logo=brave&logoColor=white)

---

> *Authomate is my personal toolkit for building backend systems efficiently and consistently.*
