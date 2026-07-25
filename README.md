# 🏠 Home Assistant Blueprints

Коллекция blueprint'ов и автоматизаций для Home Assistant. Управление списками через Telegram, синхронизация To-do списков и полезные скрипты.

---

## 📋 Telegram To-do List

Blueprint'ы для управления списками покупок/дел через Telegram-бота.

| Проект | Описание | Язык |
|--------|----------|------|
| [Telegram To-do List (RU)](telegram-todo-list-ru/) | Полнофункциональный blueprint с inline-кнопками, reply-клавиатурой и поддержкой скриптов синхронизации | 🇷🇺 Русский |
| [Telegram To-do List](telegram_to_do_list.yaml) | Базовый вариант — inline-кнопки, переключение Active/All, защита от дублей, HA 2026.04+ | 🇬🇧 English |
| [Telegram To-do List + Scripts](telegram_to_do_list_with_scripts.yaml) | Вариант с поддержкой скриптов синхронизации (до 3 скриптов), HA 2025.12+ | 🇬🇧 English |
| [Telegram To-do List TEST](todo_test.yaml) | Тестовая версия русского blueprint'а | 🇷🇺 Русский |

---

## 🔄 Синхронизация To-do списков

Скрипты и автоматизации для синхронизации данных между To-do списками.

| Проект | Описание | Тип |
|--------|----------|-----|
| [Sync To-Do Lists](Sync%20lists/sync_lists_manual.yaml) | Ручная синхронизация активных пунктов между списками (по UID). Два режима: добавление новых / полная двусторонняя синхронизация | Script blueprint |
| [Todo — Auto sync new items](Auto_Sync_Todo/auto_sync_todo_new.yaml) | Автоматическая синхронизация только новых пунктов через diff по helper | Automation blueprint |
| [Todo — Sync NEW items only](Sync_todo/auto_sync_todo_new.yaml) | Автоматическая синхронизация новых пунктов через polling + diff (совместимо с HA 2026+) | Automation blueprint |

---

## ⚡ Автоматизации

| Проект | Описание | Тип |
|--------|----------|-----|
| [Push updates to Telegram](automations/push_todo_to_telegram.yaml) | Отправляет обновлённый список в Telegram при изменении To-do в Home Assistant (вне бота) | Automation |

---

## 🚀 Быстрый старт

1. Выберите blueprint из таблицы выше
2. Импортируйте его в Home Assistant: **Настройки → Автоматизации → Blueprints → Импорт**
3. Создайте автоматизацию на основе blueprint'а
4. Укажите необходимые параметры (сущность `todo`, `chat_id`, `config_entry_id`)

## 📁 Структура репозитория

```
blueprints/
├── telegram-todo-list-ru/       # 🇷🇺 Telegram To-do List (полный)
├── telegram_to_do_list.yaml     # 🇬🇧 Telegram To-do List (базовый)
├── telegram_to_do_list_with_scripts.yaml  # 🇬🇧 Telegram To-do + Scripts
├── todo_test.yaml               # Тестовый blueprint
├── Auto_Sync_Todo/              # Авто-синхронизация (diff)
├── Sync_todo/                   # Синхронизация (polling)
├── Sync lists/                  # Ручная синхронизация
└── automations/                 # Push-уведомления в Telegram
```

## 📋 Требования

- Home Assistant **2025.12+** (некоторые blueprint'ы требуют 2026+)
- Интеграция **Telegram Bot** (настроенная с известным Config Entry ID)
- Сущности **todo** (сервисы `todo.add_item`, `todo.update_item`, `todo.remove_completed_items`, `todo.get_items`)
