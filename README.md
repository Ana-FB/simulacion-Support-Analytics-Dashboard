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

### `support_conversations`
Tabla principal con los registros de atención.

Campos principales:
- `conversation_id`
- `customer_id`
- `agent_id`
- `category_id`
- `channel_id`
- `issue_status`
- `customer_issue`
- `created_date`
- `closed_date`
- `first_response_time`
- `resolution_time`
- `reopen_count`
- `sla_met`
- `csat_score`
- `sentiment_score`

---

### `customers`
Información de los clientes:

- `customer_id`
- `full_name`
- `email`
- `phone`
- `registered_date`
- `country_code`
- `country_name`
- `city`
- `gender`
- `age`

---

### `agent`
Información de agentes de soporte:

- `agent_id`
- `agent_name`
- `role`
- `specialty`
- `agent_category_id`

---

### `channels`
Canales de entrada:

- `channel_id`
- `channel_name`

---

### `categories`
Clasificación de los casos:

- `category_id`
- `issue_category`
- `sub_category`

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
