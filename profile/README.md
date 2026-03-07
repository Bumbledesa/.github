# 🚀 Bumbledesa - Arquitectura del Sistema

## 📋 Visión General

El sistema está compuesto por los siguientes componentes principales:

- **1** aplicación móvil para estudiantes
- **1** aplicación web de backoffice para administradores
- **3** microservicios backend
- Infraestructura de despliegue y monitoreo

---

## 📦 Repositorios Principales

| Repositorio | Descripción |
|-------------|-------------|
| `Bumbledesa-mobile` | Aplicación móvil para estudiantes |
| `Bumbledesa-backoffice-web` | Panel de administración web |
| `Bumbledesa-backend` | Microservicios (auth, social, location) |
| `Bumbledesa-infra` | Infraestructura y despliegue |

---

## 🏷️ Sistema de Labels en Backlogs

### Prioridad
- `obligatorio` - Funcionalidad crítica
- `optativo` - Funcionalidad adicional

### Iteraciones
`E1` | `E2` | `E3` | `E4` | `E5`

### Repositorios
- `repo:mobile` - Cambios en la app móvil
- `repo:backoffice` - Cambios en el backoffice web
- `repo:backend` - Cambios en los microservicios
- `repo:infra` - Cambios en infraestructura

### Microservicios Backend
- `svc:auth` - Servicio de autenticación
- `svc:social` - Servicio de funcionalidades sociales
- `svc:location` - Servicio de geolocalización

### Tags Cruzados
- `touches:mobile` - Impacta la app móvil
- `touches:backend` - Impacta el backend
- `touches:backoffice` - Impacta el backoffice

---

## 🏗️ Arquitectura del Sistema

```
┌─────────────────┐
│   Mobile App    │
└────────┬────────┘
         │
┌────────┴────────┐
│ Backoffice Web  │
└────────┬────────┘
         │
         ▼
┌─────────────────────────┐
│   API / Microservices   │
├─────────────────────────┤
│  ┌─ Auth Service        │
│  ├─ Social Service      │
│  └─ Location Service    │
└──────────┬──────────────┘
           │
           ▼
   ┌───────────────┐
   │  Bases de     │
   │  Datos        │
   ├───────────────┤
   │  PostgreSQL   │
   │  MongoDB      │
   └───────────────┘
```

---

## 🧪 Estrategia de Testing

Cada microservicio incluirá:

### ✅ Tests Unitarios
> Verifican la lógica de negocio de funciones individuales

### 🔗 Tests de Integración
> Validan la interacción entre componentes internos y dependencias externas

### ⚡ Tests de Estrés
> **Específicos del location-service**  
> Simulan múltiples usuarios enviando ubicaciones para validar el comportamiento bajo carga

---

## 🔄 CI/CD Pipeline

Utilizaremos **GitHub Actions** para automatizar todo el proceso de integración y despliegue:

- 🔨 **Build** del proyecto
- 🧪 **Ejecución** de tests
- 📊 **Verificación** de cobertura de código
- 🐳 **Construcción** de imágenes Docker
- ☁️ **Despliegue** en entorno cloud

## Observabilidad y Monitoreo

---

## 📊 Observabilidad y Monitoreo

El sistema incluye herramientas profesionales para monitorear su funcionamiento en tiempo real:

| Herramienta | Función |
|-------------|---------|
| **Prometheus** | 📈 Recolección de métricas del sistema |
| **Grafana** | 📉 Visualización mediante dashboards interactivos |

**Beneficios:**
---

## 🛡️ Rate Limiting

El **location-service** implementa mecanismos de protección mediante rate limiting:

- 🚦 **Control de tráfico** - Regulación del flujo de peticiones
- 🔒 **Prevención de abusos** - Protección contra uso indebido
- 💪 **Resiliencia** - Protección del sistema ante picos de carga

---
