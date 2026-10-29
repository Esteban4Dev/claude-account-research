# Claude Account Banning Mechanism: Reverse-Engineered Analysis
# Análisis del Sistema de Baneos de Claude (Ingeniería Inversa)

This repository contains an analysis of the findings shared by the Chinese community regarding Anthropic Claude's internal account banning and suspension mechanism, which operates on an invisible points system.

Este repositorio contiene un análisis de los hallazgos de la comunidad china sobre cómo funciona el mecanismo interno de baneos y suspensiones de cuentas de Claude de Anthropic, el cual opera bajo un sistema de puntuación invisible.

---

## 📂 Repository Structure / Estructura del Repositorio

* `reverse-engineering-claude.md` / `reverse-engineering-claude.txt`: Complete bilingual breakdown of the factors affecting account scoring (Registration, Payments, Usage, IP & Devices, Account Age, and Observation Periods).

---

## 🔍 Key Findings Summary / Resumen de Hallazgos Clave

* **Points System (Sistema de Puntos):** Accounts start with a base score and gain or drop points based on behavior. Falling below the threshold triggers an automatic ban.
* **Registration & IP (Registro e IP):** Clean IPs and avoiding immediate KYC are critical. Mobile registration adds points.
* **Payments (Pagos):** Immediate subscriptions or jumping straight to "Max" plans heavily penalize accounts. Foreign bank cards add trust points.
* **Usage & Devices (Uso y Dispositivos):** Official desktop and mobile clients grant small score boosts, while frequent IP switching, multi-device logins, and Linux usage deduct points.
* **Observation Period (Periodo de Observación):** Sudden logouts indicate entering a review threshold before a potential ban.

---

## 🌐 Languages / Idiomas

The main documentation is provided in both **English** and **Español** within the text/markdown files.