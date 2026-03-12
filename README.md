# 🧠 Анализатор конкурентов в нише ментального здоровья

MVP AI-ассистент для конкурентного анализа платформ онлайн-терапии и психологической помощи.

![Python](https://img.shields.io/badge/Python-3.9+-blue.svg)
![FastAPI](https://img.shields.io/badge/FastAPI-0.104+-green.svg)
![OpenAI](https://img.shields.io/badge/OpenAI-GPT--4o--mini-purple.svg)

## 🎯 Кейс

Анализируем конкурентов в нише ментального здоровья: **Youtalk, Zigmund.Online, Alter, BetterHelp, Woebot**.

Для каждого конкурента система оценивает:
- Позиционирование в нише (`mental_health_positioning`)
- Доверие визуального дизайна (`trust_score` 0–10) — критично для психологических сервисов
- Эмоциональный тон лендинга (`emotional_tone`)
- Сильные/слабые стороны и рекомендации

## 🚀 Быстрый старт

```bash
# Клонируй репо
git clone <repo-url>
cd pem08

# Создай виртуальное окружение
python -m venv venv
source venv/bin/activate  # Mac/Linux
# venv\Scripts\activate   # Windows

# Установи зависимости
pip install -r requirements.txt

# Настрой .env
cp env.example.txt .env
# Вставь свой OPENAI_API_KEY в .env

# Запуск
python run.py
```

Открой: http://localhost:8000
Swagger: http://localhost:8000/docs

## 📡 API эндпоинты

| Метод | URL | Описание |
|-------|-----|----------|
| POST | `/analyze_text` | Анализ текста конкурента |
| POST | `/analyze_image` | Анализ скриншота/баннера |
| POST | `/parse_demo` | Парсинг сайта по URL (Selenium) |
| GET | `/history` | История последних запросов |

## 📁 Структура

```
├── backend/
│   ├── main.py              # FastAPI приложение
│   ├── config.py            # Конфиг + список конкурентов
│   ├── models/schemas.py    # Pydantic схемы
│   └── services/
│       ├── openai_service.py    # GPT-4o-mini анализ
│       ├── parser_service.py    # Selenium парсер
│       └── history_service.py   # История
├── frontend/                # HTML/JS интерфейс
├── data/                    # Скриншоты конкурентов
├── run.py                   # Точка входа
└── env.example.txt          # Пример .env
```

## 🛠️ Технологии

- **FastAPI** — REST API
- **OpenAI GPT-4o-mini** — анализ текста и изображений (Vision)
- **Selenium + ChromeDriver** — автопарсинг сайтов конкурентов
- **Pydantic** — валидация и JSON-схемы ответов

## ⚙️ Переменные окружения

```env
OPENAI_API_KEY=sk-...
OPENAI_MODEL=gpt-4o-mini
OPENAI_VISION_MODEL=gpt-4o-mini
```

> ⚠️ Никогда не коммить `.env` — он в `.gitignore`
