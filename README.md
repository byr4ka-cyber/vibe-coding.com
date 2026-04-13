# ВАЙБ-КОДИНГ

**Вайб-Кодинг** — язык программирования на естественном языке с упором на простоту, ИИ и живой CLI. Пользователь пишет команды так, как говорит, а система интерпретирует, дополняет и выполняет их.

Целевой домен проекта: https://vibecoding.ai

> Внимание: пока этот домен не опубликован. Чтобы сайт открывался для всех, нужно развернуть содержимое папки `site/` на публичном хостинге.

## Основные возможности

- натуральный язык вместо жесткого синтаксиса
- автоматическая типизация и переменные без объявления типов
- встроенная команда `ai` для генерации и коррекции кода через ИИ
- минимальное количество ключевых слов
- режимы: `chill`, `pro`, `chaos`
- команды: `print`, `set`, `if`, `vibe`, `chill`, `ai`, `fix`
- работа с файлами, простые интерфейсы и интернет-запросы
- интерактивный REPL и запуск `.vibe` файлов

## Установка

```bash
npm install -g vibe-coding
```

Для работы ИИ установите ключ для OpenAI:

```bash
export VIBE_API_KEY=your_openai_key
# или на Windows PowerShell:
$env:VIBE_API_KEY="your_openai_key"
```

Чтобы выбрать локальный ИИ, задайте провайдера:

```bash
vibe --ai-provider local examples/hello.vibe
```

или через переменную окружения:

```bash
export VIBE_AI_PROVIDER=local
```

## Быстрый старт

```bash
vibe repl
```

или

```bash
vibe examples/hello.vibe
```

## Режимы

- `chill` — самый прощающий, игнорирует мелкие ошибки и исправляет их.
- `pro` — строгий, выдает ошибки при неправильном синтаксисе.
- `chaos` — свободный, пытается интерпретировать любые неточные фразы.

```bash
vibe --mode chaos examples/hello.vibe
```

## Структура проекта

- `src/cli.js` — командная строка и REPL
- `src/interpreter.js` — движок интерпретации Вайб-Кодинга
- `src/ai.js` — интеграция с AI API и локальной моделью
- `src/utils.js` — утилиты для анализа и исправления текста
- `examples/` — демонстрационные файлы, включая `local-ai.vibe`
- `docs/` — документация и справочник

## Локальный сайт

```bash
npm run site
```

## Пакеты и установщики

Собери бинарники и архивы для Windows/macOS/Linux:

```bash
npm run build:installers
```

После этого в `dist/installers/` появятся:

- `vibe-setup.exe` (Windows)
- `vibe-macos` (macOS)
- `vibe-linux` (Linux)
- `vibe-windows.zip`
- `vibe-macos.zip`
- `vibe-linux.tar.gz`

Для Windows запусти `vibe-setup.exe`.

Для macOS:

```bash
chmod +x vibe-macos
./vibe-macos
```

Для Linux:

```bash
tar -xzf vibe-linux.tar.gz
chmod +x vibe-linux
```

Откроется страница проекта по адресу http://localhost:8080

## Публикация домена

Проект ориентирован на домен `https://vibecoding.ai`.

Чтобы опубликовать сайт, разместите содержимое папки `site/` на любом статическом хостинге, например GitHub Pages, Netlify или Vercel.

Если домен уже зарегистрирован, настройте DNS:

- `A` запись: IP адрес сервера/платформы
- `CNAME` запись: адрес хостинга, если он поддерживает CNAME

Подробнее см. `docs/domain.md`.

## Сборка установщиков

```bash
npm install
npm run build
npm run build:installers
```

Скрипт создаст архивы `dist/installers` и подготовит инструкции для DMG/AppImage/deb.
