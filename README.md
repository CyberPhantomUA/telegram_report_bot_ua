# Юзер-Бот, що автоматизує репортування Телеграм каналів пропагандистів

Цей Телеграм Юзер-Бот використовується для автоматизації репорту пропагандистьских каналів. 

## Інсталяція 
1. По-перше, вам необхідно інсталювати Python3. Python можна завантажити за [посиланням](https://www.python.org/). Також треба [завантажити git](https://git-scm.com/download/win) (натискаємо на "Click here to download" зверху, під час встановлення декілька раз натискаємо Next. Далі перезавантажуємо комп'ютер).
2. Запустіть консоль. Для цього використовуйте комбінацію клавіш Win+R, у з'явившомуся вікні напишіть cmd та натисніть enter
3. Далі виконуємо наступні команди:
```
git clone https://github.com/IgorKovr/telegram_report_bot_ua
cd telegram_report_bot_ua
pip install -r requirements.txt
```
4. Переходимо за посиланням  https://my.telegram.org/, вводимо свій номер телефону та код авторизації
<br>Переходимо у вкладку API development tools, пишемо любий App title та Short name
<br>Нагорі отримуємо App api_id та App api_hash
<br>**ПЕРЕДАВАТИ КОМУСЬ `api_id` та `api_hash` НІ В ЯКОМУ РАЗІ НЕ МОЖНА!!! Вони дают можливіть контролювати вашу персональну сторінку у Телеграмі.**

## Використання 
1. Далі запускаємо бота:`python main.py` або `python3 main.py`
2. По черзі вводимо:
- App api_id
- App api_hash
- Телефон вашого аккаунта у форматі +380ххххххххх
- Код автентифікації який прийде повідомленням у телеграм
3. Бот автоматично напише репорти на випадкові 150 каналів з файлу `telegram_db`.
<br>**Правильно налаштована програма буде відображати такий результат:**
<br><br>![image](https://user-images.githubusercontent.com/39994538/155859028-e83b5228-e711-4f21-bf4e-db9b1cfccb24.png)

Щоб використати інший аккаунт, треба видалили файл session_new.session у папці з програмою (або використати команду `del session_new.session`).

## Оновлення боту та бази каналів
Ми намагаємося періодично оновляти самого бота та базу пропагадистських каналів, тому рекомендуємо іноді перевіряти чи не додались нові канали. 
Якщо ви хочете оновити базу та/чи бота вам необхідно: 
1. Зайти у теку проекту
2. Відкрити консоль у цій теці 
3. Вписати команду 
``` 
git pull
```
4. База та бот оновлені, можете як вказано вище запускати бота та відсилати репорти на більшу кількість пропагандистів.


## Безпека телеграм-акаунту
Під час налаштування бота вам буде потрібно вказати одноразовий код на сайті my.telegram.org та у python модулі [telethon](https://github.com/LonamiWebs/Telethon). Перше - це офіційний сайт телеграму, друге - це дуже відомий модуль, код якого був перевірений досвідченими програмістами не один раз. Тож ваш акаунт не передається третім особам на протязі всього процесу налаштування та використання програми.
<br>Також програма емулює поведінку нового пристрою який використовує ваш акаунт. Ви можете побачити цей віртуальний пристрій в активних сеансах телеграму (Налаштування -> Приватність і безпека  -> Показати всі сеанси). Він матиме таку ж назву і тип які ви вкажете під час реєстрації на my.telegram.org. *Після виконання програми ви можете видалити цей девайс з активних сеансів.*

## Додаткова інформація
У теці проєкту знаходиться файл `telegram_db`, що містить у собі список пропагандистських каналів. Якщо ви маєте інформацію про інші канали, що не війшли у список, але заслуговують репорту - присилайте їх мені у [телеграм](https://www.t.me/IgorKovr) або додавайте їх у реквестах на Github.
