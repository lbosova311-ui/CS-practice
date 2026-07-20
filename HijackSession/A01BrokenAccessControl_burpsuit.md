## Мета: Знайомство з A01:2025 Broken Access Control

### Середовище: Kali Linux, Docker engine, OWASP WebGoat container.

В меню обрали:
![hijacksession1](image.jpg)

Запускаємо Burpsuit, переходимо на вкладинку "Proxy", запускаємо браузер, в якому відкриваємо "WebGoat" та створюємо користавача і логінуємся або одразу логінуємось (якщо не видаляли контейнер) та переходимо на другий крок. Натискаємо "Access", отримуємо помилку:
![hijacksession1](image3.jpg)

Повертаємось до burpsuit, де маємо передивитись вкладинку HTTPhistory:
![hijacksession1](image4.jpg)

Далі шукаємо відповідь POST, в якої міститься інформація про цю помилку (ключ - це зміст hijack_cookie, яку нам і потрібно "передбачити"):
![hijacksession1](image5.jpg)
![hijacksession1](image6.jpg)

Далі натискаємо праву кнопку миші та відправляємо запит до Repeater.В Repeater робимо декілька повторів (в цьому прикладі може вистачити 5+ запитів): 
![hijacksession1](image7.jpg)

Бачимо, як змінюється значення hijack_cookie, копіюємо ці значення в текстовий редактор:
![hijacksession1](image8.jpg)
