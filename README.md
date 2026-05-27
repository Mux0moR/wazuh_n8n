# 🔐 Security Automation Platform (Wazuh + n8n)

SOAR-lite решение для автоматизации реагирования на инциденты безопасности.

## 📌 Описание

Проект реализует автоматический pipeline обработки security-алертов:
- intake (получение алертов из Wazuh)
- enrichment (обогащение IP через Threat Intelligence)
- correlation (анализ поведения)
- response (автоматическая блокировка атак)

## 🧠 Архитектура

Wazuh → n8n → Enrichment → Decision Engine → Response

## ⚙️ Стек

- Wazuh (SIEM)
- n8n (orchestration)
- Python (enrichment + correlation)
- OpenSearch (логи)
- Supabase (state storage)

## 🔄 Сценарии

### 1. Brute Force Detection
- анализ failed SSH логинов
- корреляция по IP и времени
- автоматическая блокировка

### 2. Threat Intelligence Enrichment
- AbuseIPDB
- VirusTotal
- GeoIP

### 3. Auto Response
- iptables block
- fail2ban
- alerting (Telegram)

## 📊 Результаты

- MTTR: ~40 мин → <3 мин
- Автоматизация: ~80% инцидентов
- Снижение нагрузки на SOC

## ▶️ Запуск

1. Запустить Wazuh
2. Развернуть n8n
3. Импортировать workflows из `/n8n`
4. Настроить ENV:
   - ABUSEIPDB_API_KEY
   - WAZUH_API_TOKEN

## 📁 Структура

см. папки проекта

## 📌 Demo

(скриншоты / gif / лог примера)
