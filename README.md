# ⚙️ Support Analytics Dataset

## Sector de Negocio
Cross-Industry

---

## 📦 Descripción

Este repositorio contiene un **dataset simulado de conversaciones de soporte** utilizado para desarrollar un dashboard analítico de atención al cliente y comunidad.

Los datos representan registros exportados desde canales como WhatsApp o sistemas CRM.

---

## 🎯 Objetivo de la Simulación

El objetivo del dataset es permitir la creación de un panel que mida:

- Tiempo de respuesta  
- Volumen de consultas  
- Temas recurrentes  
- Rendimiento por canal y agente  
- Satisfacción del cliente  

---

## 🗂 Estructura del Dataset

El modelo está compuesto por las siguientes tablas:

---

## 📁 Tabla: `support_conversations`

| Columna               | Tipo      | Descripción                                                                      |
| --------------------- | --------- | -------------------------------------------------------------------------------- |
| `conversation_id`     | VARCHAR   | Identificador único de la conversación de soporte.                               |
| `customer_id`         | VARCHAR   | ID del cliente que inició la consulta (FK hacia `customers`).                    |
| `agent_id`            | VARCHAR   | ID del agente que atendió la conversación (FK hacia `agent`).                    |
| `category_id`         | VARCHAR   | ID de la categoría del problema (FK hacia `categories`).                         |
| `channel_id`          | VARCHAR   | ID del canal de entrada del caso (FK hacia `channels`).                          |
| `issue_status`        | VARCHAR   | Estado actual del caso (`open`, `pending`, `resolved`, `closed`).                |
| `customer_issue`      | TEXT      | Descripción textual del problema reportado por el cliente.                       |
| `created_date`        | TIMESTAMP | Fecha y hora de creación del caso.                                               |
| `closed_date`         | TIMESTAMP | Fecha y hora de cierre del caso.                                                 |
| `first_response_time` | INTEGER   | Tiempo hasta la primera respuesta, en minutos.                                   |
| `resolution_time`     | INTEGER   | Tiempo total hasta la resolución, en minutos.                                    |
| `reopen_count`        | INTEGER   | Cantidad de veces que el caso fue reabierto.                                     |
| `sla_met`             | BOOLEAN   | Indica si se cumplió el (SLA)**es el compromiso de tiempo de respuesta y resolución establecido por la empresa para atender los casos de soporte.** (`Yes`/`No`). |
| `csat_score`          | INTEGER   | Puntuación de satisfacción del cliente (escala 1–5).                             |
| `sentiment_score`     | INTEGER   | Puntaje de sentimiento del cliente (ej: -5 a 5).                                 |

---

## 👥 Tabla: `customers`

| Columna           | Tipo       | Descripción                                           |
| ----------------- | ---------- | ----------------------------------------------------- |
| `customer_id`     | VARCHAR    | Identificador único del cliente.                      |
| `full_name`       | VARCHAR    | Nombre completo del cliente.                          |
| `email`           | VARCHAR    | Correo electrónico.                                   |
| `phone`           | VARCHAR    | Teléfono del cliente.                                 |
| `registered_date` | DATE       | Fecha en que el cliente fue registrado en el sistema. |
| `country_code`    | VARCHAR(2) | Código del país (ISO-2: AR, BR, MX, etc.).            |
| `country_name`    | VARCHAR    | Nombre del país.                                      |
| `city`            | VARCHAR    | Ciudad de residencia.                                 |
| `gender`          | VARCHAR    | Género declarado.                                     |
| `age`             | INTEGER    | Edad del cliente.                                     |

---

## 🎧 Tabla: `agent`

| Columna             | Tipo    | Descripción                                                  |
| ------------------- | ------- | ------------------------------------------------------------ |
| `agent_id`          | VARCHAR | Identificador único del agente.                              |
| `agent_name`        | VARCHAR | Nombre completo del agente.                                  |
| `role`              | VARCHAR | Rol del agente (Junior, Senior, Supervisor).                 |
| `specialty`         | VARCHAR | Especialidad del agente (Técnico, Facturación, Retención).   |
| `agent_category_id` | VARCHAR | Categoría principal que atiende (relación con `categories`). |

---

## 🌐 Tabla: `channels`

| Columna        | Tipo    | Descripción                                               |
| -------------- | ------- | --------------------------------------------------------- |
| `channel_id`   | VARCHAR | Identificador único del canal.                            |
| `channel_name` | VARCHAR | Nombre del canal (Email, Chat, WhatsApp, Teléfono, etc.). |

---

## 🏷 Tabla: `categories`

| Columna          | Tipo    | Descripción                                                          |
| ---------------- | ------- | -------------------------------------------------------------------- |
| `category_id`    | VARCHAR | Identificador único de la categoría.                                 |
| `issue_category` | VARCHAR | Categoría principal del caso (Ej: Facturación, Soporte Técnico).     |
| `sub_category`   | VARCHAR | Subcategoría específica (Ej: Error de pago, Recupero de contraseña). |

---

## 🔗 Relaciones

- `support_conversations.customer_id` → `customers.customer_id`
- `support_conversations.agent_id` → `agent.agent_id`
- `support_conversations.channel_id` → `channels.channel_id`
- `support_conversations.category_id` → `categories.category_id`

---

## ✅ Requerimientos Cubiertos por el Dataset

Este dataset permite cumplir con los siguientes puntos de la simulación:

✔ Medición de tiempos de respuesta  
✔ Análisis de volumen por canal  
✔ Identificación de temas recurrentes  
✔ Evaluación del desempeño por agente  
✔ Seguimiento de satisfacción (CSAT y sentimiento)  

---

## 📌 Nota

Este dataset es **100% ficticio**, creado exclusivamente para fines de simulación, práctica y análisis de datos.
