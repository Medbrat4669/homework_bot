# homework_bot

## _Telegram-бот для отслеживания изменений статусов работ на Яндекс.Практикуме_

### Описание проекта

Telegram-бот раз в 10 минут обращается к API сервиса Практикум.Домашка на 
эндпойнт https://practicum.yandex.ru/api/user_api/homework_statuses/ 
(требуется предварительно получить токен по адресу 
https://oauth.yandex.ru/authorize?response_type=token&client_id=1d0b9dd4d652455a9eb710d450ff456a) 
и получает информацию об изменениях статусов домашних работ на 
Яндекс.Практикуме ("работа принята на проверку", "работа возвращена для 
исправления ошибок" или "работа принята"). Если ни у одной из домашних работ 
не появился новый статус — список работ будет пуст, в противном случае бот 
отправит пользователю сообщение в Telegram об изменении статуса работы. Бот 
логирует свою работу и сообщает о проблемах сообщением в Telegram.

Стек: Python 3.7, python-telegram-bot, logging, flake8.

### Запуск проекта на локальном компьютере

Клонировать репозиторий и перейти в него в командной строке:

```
git clone git@github.com:Medbrat4669/homework_bot.git
cd homework_bot
```

Создать в корневой папке проекта файл с названием ".env" и следующим 
содержанием:

```
PRACTICUM_TOKEN=<токен для API сервиса Практикум.Домашка>
TELEGRAM_TOKEN=<токен для работы с Bot API>
TELEGRAM_CHAT_ID=<ID вашего Telegram-аккаунта>**

# Токен для работы с Bot API можно получить у Telegram бота @BotFather: 
начать диалог, нажав на кнопку Start, затем отправить команду /newbot и в 
следующих сообщениях указать имя бота (на любом языке, под этим именем бот 
будет отображаться в списке контактов) и техническое имя (должно быть 
уникальным, по нему бот можно будет найти в Telegram, техническое имя должно 
оканчиваться на слово bot, например, your_homework_bot), в случае успеха 
BotFather поздравит вас и отправит в чат токен для работы с Bot API (токен 
выглядит примерно так: 123456:ABC-DEF1234ghIkl-zyx57W2v1u123ew11).

# ID своего Telegram-аккаунта можно узнать у Telegram-бота @userinfobot, 
отправив сообщение /start.
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env

# для Linux
source env/bin/activate

# для Windows
env\Scripts\activate
# в случае с терминалом bash эта команда может не сработать, тогда следует 
перейти в папку Scripts командой
cd env/Scripts/
# и активировать виртуальное окружение, поставив впереди точку:
. activate

# деактивировать виртуальное окружение можно командой
deactivate
```

Установить зависимости из файла requirements.txt:

```
python3 -m pip install --upgrade pip
pip install -r requirements.txt
```

Локально запустить бота:

```
python3 homework.py
```

Остановить работу бота можно командой Ctrl + C.

### Авторы
Чугин Владислав