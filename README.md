# 🏠 Home Assistant Scripts

Коллекция blueprint'ов и автоматизаций для Home Assistant. Управление списками через Telegram, синхронизация To-do списков и полезные скрипты.

---

## 📋 Telegram To-do List

Blueprint'ы для управления списками покупок/дел через Telegram-бота.

| Проект | Описание | Язык | Импорт |
|--------|----------|------|--------|
| [Telegram To-do List (RU)](telegram-todo-list-ru/) | Полнофункциональный blueprint с inline-кнопками, reply-клавиатурой и поддержкой скриптов синхронизации | 🇷🇺 Русский | <a href="https://my.home-assistant.io/redirect/blueprint_import/?blueprint_url=https%3A%2F%2Fgithub.com%2FurtaevS%2Fblueprints%2Fblob%2Fmain%2Ftelegram-todo-list-ru%2Ftelegram_todo_ru.yaml" target="_blank" rel="noreferrer noopener"><img src="https://my.home-assistant.io/badges/blueprint_import.svg" alt="Open your Home Assistant instance and show the blueprint import dialog with a specific blueprint pre-filled." /></a> |
| [Telegram To-do List + Scripts](telegram_to_do_list_with_scripts.yaml) | Вариант с поддержкой скриптов синхронизации (до 3 скриптов), HA 2025.12+ | 🇬🇧 English | |

---

## 🔄 Синхронизация To-do списков

Скрипты для синхронизации данных между To-do списками.

| Проект | Описание | Тип |
|--------|----------|-----|
| [Sync To-Do Lists](Sync%20lists/sync_lists_manual.yaml) | Ручная синхронизация активных пунктов между списками (по UID). Два режима: добавление новых / полная двусторонняя синхронизация | Script blueprint |

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
Home assistant Scripts/
├── telegram-todo-list-ru/                # 🇷🇺 Telegram To-do List (полный)
│   ├── README.md                         #    Описание проекта
│   ├── CHANGELOG.MD                      #    Журнал изменений
│   └── telegram_todo_ru.yaml             #    Blueprint
├── telegram_to_do_list_with_scripts.yaml # 🇬🇧 Telegram To-do + Scripts
├── Sync lists/                           # Ручная синхронизация списков
│   └── sync_lists_manual.yaml
└── automations/                          # Push-уведомления в Telegram
    └── push_todo_to_telegram.yaml
```

## 📋 Требования

- Home Assistant **2025.12+**
- Интеграция **Telegram Bot** (настроенная с известным Config Entry ID)
- Сущности **todo** (сервисы `todo.add_item`, `todo.update_item`, `todo.remove_completed_items`, `todo.get_items`)

---

<p align="center">
  <strong>Если этот проект оказался полезен для вас — вы можете поддержать автора ☕</strong><br>
  <em>Каждая чашечка кофе помогает создавать новые blueprint'ы и поддерживать существующие.</em>
</p>

<p align="center">
  <a href="https://pay.cloudtips.ru/p/0d93f1af" target="_blank" rel="noreferrer noopener">
    <img src="https://img.shields.io/badge/☕_Чай—CloudTips-blue?style=for-the-badge" alt="Поддержать проект" />
  </a>
</p>
