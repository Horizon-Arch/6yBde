# 6yBde


# Мониторинг изменений в файлах SC с помощью GitHub Desktop

Этот гайд поможет вам настроить отслеживание изменений в папке `assets` SC через приложение [GitHub Desktop](https://desktop.github.com/download/) и не получить блокировку за 4.1.1

> 4.1. Пользователь не вправе осуществлять следующие действия в отношении Игры:

> 4.1.1. Заменять или изменять файлы Игры, а также использовать или разрабатывать читы, эксплойты, программы, автоматизирующие Игровой процесс, ботов, моды или любое неавторизованное программное обеспечение, которое изменяет или вмешивается в Игровой процесс.

---

## 📥 Установка и настройка репозитория

1. Скачайте и установите [GitHub Desktop](https://desktop.github.com/download/).
2. Откройте приложение и нажмите **"Create a New Repository on your hard drive..."**.
3. В поле **"Local path"** укажите путь:  
   ```
   C:\Users\ВАШ_ПОЛЬЗОВАТЕЛЬ\AppData
   ```
4. В поле **"Name"** укажите:  
   ```
   Roaming
   ```
5. Нажмите кнопку **"Create repository"**.

⚠️ После создания репозитория GitHub Desktop начнёт "сканировать" всю папку `Roaming`. Чтобы ограничить область отслеживания - создайте файл `.gitignore`.

---

## ⚙️ Настройка `.gitignore`

Создайте файл `.gitignore` в папке репозитория (`Roaming`) и добавьте следующий код:

```gitignore
# Игнорировать всё
*

# Разрешить только папку EXBO
!EXBO/
!EXBO/**

# Отслеживать только assets (т.к. только там происходят значимые изменения)

EXBO/*
!EXBO/runtime/
EXBO/runtime/*
!EXBO/runtime/stalcraft/
EXBO/runtime/stalcraft/*
!EXBO/runtime/stalcraft/modassets/
EXBO/runtime/stalcraft/modassets/*
!EXBO/runtime/stalcraft/modassets/assets/
EXBO/runtime/stalcraft/modassets/assets/*
!EXBO/runtime/stalcraft/modassets/assets/**

# Исключение определённых типов файлов
EXBO/runtime/stalcraft/modassets/assets/**/*.log
EXBO/runtime/stalcraft/modassets/assets/**/*.NAME
```

Теперь репозиторий будет отслеживать изменения **только** в файлах внутри папки `assets`. В этом репозитории (`6yBde`) вы также найдёте рекомендуемый `.gitignore`, настроенный так, чтобы отслеживать только файлы, пригодные для расшифровки. Кроме того, в GitHub Desktop можно кликнуть правой кнопкой мыши на нежелательный файл и автоматически добавить его в `.gitignore`

---

## 🧩 Расшифровка файлов

Для декодирования файлов `.mcsa` / `.mcvd`, `.ol`, `.mic` вы можете использовать [scfile](https://github.com/onejeuu/sc-file):

- Релизы: [sc-file-releases](https://github.com/onejeuu/sc-file/releases)

---

## ✅ Всё!

Обновив игру, вы будете видеть все изменения в файлах, произошедшие во время тех. работ.

