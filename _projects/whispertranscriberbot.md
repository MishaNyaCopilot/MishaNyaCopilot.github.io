---
layout: project
title: WhisperTranscriberBot
subtitle: AI Telegram Bot for Voice-to-Text Transcription with Monetization and Monitoring
date: 2024-06-01
featured: true
tech: ["Python", "Telegram API", "FastAPI", "PostgreSQL", "Redis", "Docker", "Streamlit", "Whisper AI", "Microservices"]
role: Full-Stack Developer
status: Actively Maintained
cover: /assets/images/whispertranscriberbot/cover.png # Убедись, что путь к изображению обложки верный
images:
  - src: /assets/images/whispertranscriberbot/screenshot_main.png # Скриншот из слайда 10 (основная функциональность)
    alt: Main transcription feature
    caption: Core transcription functionality
  # - src: /assets/images/whispertranscriberbot/screenshot_monetization_flow.png # Скриншот из слайда 11 (монетизация)
  #   alt: Monetization flow screenshots
  #   caption: WSC purchase and ToS agreement flow
  - src: /assets/images/whispertranscriberbot/architecture_diagram.png # Скриншот из слайда 7 (схема взаимодействия)
    alt: Microservice architecture diagram
    caption: Detailed microservices interaction diagram
  - src: /assets/images/whispertranscriberbot/db_schema.png # Скриншот из слайда 8 (ER-диаграмма)
    alt: Database ER-diagram and schema
    caption: PostgreSQL database schema and table descriptions
  - src: /assets/images/whispertranscriberbot/streamlit_dashboard.png # Скриншот твоего дашборда на Streamlit
    alt: Analytics Dashboard
    caption: Real-time bot analytics and system monitoring dashboard
links:
  # repo: https://github.com/MishaNya/WhisperTranscriberBotDocker # Замени на актуальную ссылку на GitHub
  extra:
    - label: Попробуйте сами
      url: https://t.me/WHISPERTRANSCRIBER_BOT
---

## Description

Я разработал **WhisperTranscriberBot** — Telegram-бота, который позволяет пользователям транскрибировать голосовые и видеосообщения, а также аудио- и видеофайлы (MP3, MP4, OGG и др.) прямо в мессенджере. Проект реализован с использованием микросервисной архитектуры, что обеспечивает высокую надежность и масштабируемость.

### Key Features & Innovations

*   **Высококачественная транскрибация:** Использование передовой AI-модели **Whisper Large-v3** от OpenAI через оптимизированную библиотеку `faster-whisper` обеспечивает выдающуюся точность распознавания речи даже в сложных условиях. Бот поддерживает автоматическое определение и транскрибацию на 99 языках.
*   **Широкая поддержка медиаформатов:** Помимо стандартных голосовых и видеосообщений, бот обрабатывает прикрепленные аудио- и видеофайлы, что значительно расширяет его применимость.
*   **Гибкая монетизация через Telegram Stars (XTR):** Внедрена прозрачная система оплаты за транскрибацию сверх ежедневного бесплатного лимита. Это обеспечивает удобный и понятный механизм монетизации без навязчивой рекламы.
*   **Многоязычный интерфейс:** Пользователи могут выбирать язык интерфейса бота, а также настраивать язык транскрибации.
*   **Масштабируемая микросервисная архитектура:**
    *   **Основной Telegram Бот (Python):** Управляет взаимодействием с пользователем, логикой команд, платежами и очередями.
    *   **Сервис Транскрибации (Python, FastAPI):** Высокопроизводительный сервис для самой транскрибации, поддерживающий GPU-ускорение.
    *   **PostgreSQL:** Надежная база данных для хранения всех пользовательских, чатовых данных, записей о транскрибациях и платежах.
    *   **Redis:** Используется для эффективного управления очередью отправки сообщений Telegram и ограничения частоты запросов (Rate Limiter).
*   **Оптимизированная обработка файлов:** Вместо загрузки файлов на сервер бота, реализована передача `file_path` напрямую между `telegram-bot-api` и сервисом транскрибации через **общий Docker-том**. Это минимизирует задержки и накладные расходы.
*   **Система Мониторинга:** Разработан **дашборд на Streamlit** для мониторинга производительности и здоровья системы в реальном времени. Дашборд отображает ключевые метрики (CPU, RAM, GPU), а также статистику по пользователям, транскрипциям и платежам.

### Impact & Scale

Бот активно используется и успешно функционирует, обрабатывая запросы от значительной пользовательской базы:
*   **Пользовательских чатов:** 1010
*   **Групповых/канальных чатов:** 174
*   **Общее количество участников в группах/каналах:** 34309

Эти показатели подтверждают востребованность решения и его стабильную работу под нагрузкой.

### Next Steps & Future Vision

Я не останавливаюсь на достигнутом и уже сейчас разрабатываю планы по полной переработке WhisperTranscriberBot на **Golang**. Переход на Go позволит создать еще более высокопроизводительную и ресурсоэффективную систему, а также реализовать новую, более гибкую архитектуру, которая откроет путь к значительному расширению функционала и дальнейшей оптимизации.