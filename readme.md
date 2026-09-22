# Linux Learning Journey

## Содержание
1. [Развертывание среды](#развертывание-среды)
2. [Базовые команды CLI](#базовые-команды-cli)
3. [Менеджер пакетов APT](#менеджер-пакетов-apt)
4. [Git основы](#git-основы)
5. [SSH и безопасность](#ssh-и-безопасность)

## Развертывание среды
- **ОС:** Ubuntu Server 22.04 LTS
- **Виртуализация:** VirtualBox
- **Сеть:** Bridged (сетевой мост)
- **SSH-клиент:** MobaXterm / PowerShell

## Базовые команды CLI

### Навигация
```bash
pwd     # Показать текущую директорию
ls      # Список файлов
ls -la  # Все файлы (включая скрытые)

cd <путь>   # Перейти в директорию
cd ..       # На уровень вверх
mkdir <имя> # Создать директорию
```

### Работа с файлами
```bash
cat <файл>  # Вывести содержимое файла
nano <файл> # Редактировать файл

cp <откуда> <куда>  # Копировать
mv <откуда> <куда>  # Переместить/переименовать

rm <файл>       # Удалить файл
rm -rf <папка>  # Удалить папку рекурсивно
```

## Менеджер пакетов APT
```bash
sudo apt update              # Обновить список пакетов
sudo apt upgrade -y          # Обновить установленные пакеты
sudo apt install <пакет>     # Установить пакет
sudo apt remove <пакет>      # Удалить пакет
sudo apt search <пакет>      # Поиск пакета
```

Пример
```bash
sudo apt update && sudo apt install htop curl git -y
```

## Git основы

### Первичная настройка
```bash
git config --global user.name "mbddd"
git config --global user.email "sl_mc1@mail.ru"
```

### Основные команды
```bash
git init                          # Инициализировать репозиторий
git status                        # Показать статус изменений
git add <файл>                    # Добавить файл в индекс
git add .                         # Добавить все файлы
git commit -m "сообщение"         # Создать коммит
git push                          # Отправить в удаленный репозиторий
git pull                          # Получить изменения из репозитория
git log                           # История коммитов
```

### Привязка remote-репозитория
```bash
git remote add origin git@github.com:username/repository.git
```

### Отправка первой версии
```bash
git branch -M main      # меняем имя ветки
git push -u origin main
```

## SSH и безопасность

### Генерация SSH-ключа
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

### Просмотр публичного ключа
```bash
cat ~/.ssh/id_ed25519.pub
```

### Генерация ключей
```bash
ssh-keygen -t ed25519 -C "your_email@example.com"
```

### Подключение по SSH
```bash
ssh user@xxx.xxx.xxx.xxx
```

### Проверка SSH-сервиса на сервере
```bash
sudo systemctl status ssh
sudo systemctl enable ssh
sudo systemctl restart ssh
```

