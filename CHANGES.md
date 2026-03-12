# Адаптация под нишу: ментальное здоровье / онлайн-терапия

## Что изменено

### 1. Переход с ProxyAPI на OpenAI
- `backend/config.py` — `base_url` изменён с `proxyapi.ru` на `api.openai.com/v1`
- Переменная окружения: `PROXY_API_KEY` → `OPENAI_API_KEY`

### 2. Новые поля в схемах (`backend/models/schemas.py`)

**CompetitorAnalysis** (анализ текста):
- `mental_health_positioning` — как компания позиционирует себя в нише ментального здоровья

**ImageAnalysis** (анализ изображений):
- `trust_score` (0–10) — насколько дизайн внушает доверие и безопасность
- `emotional_tone` — эмоциональный тон визуала (спокойный, тёплый, холодный и т.д.)

### 3. Адаптация промптов (`backend/services/openai_service.py`)

**analyze_text**: модель теперь выступает экспертом именно в нише ментального здоровья, заполняет `mental_health_positioning`.

**analyze_image**: модель оценивает доверие (`trust_score`) и эмоциональный тон (`emotional_tone`) — ключевые метрики для психологических сервисов.

## Ниша проекта
Конкуренты в сфере онлайн-терапии и ментального здоровья: Youtalk, Zigmund.Online, Alter, BetterHelp, Woebot.
