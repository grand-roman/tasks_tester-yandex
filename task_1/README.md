# Задание 1

Вы написали view-функцию, обрабатывающую URL `/new_post/`, которая на **GET** запрос отвечает страницей с формой, а на **POST** - создает новый пост из данных формы и редиректит на главную страницу.  
Опишите юнит-тесты, которые вы бы написали для этой view-функции.  

В этом задании код писать не нужно, опишите что по вашему мнению тут нужно/можно протестировать, и почему это нужно сделать именно так, как вы предлагаете.

# Ответ на Задание 1

Имеет смысл протестировать, что
1. после успешной валидации в модели нового поста появится новый post;
2. после отправки валидной формы происходит переадресация на на главную страницу. 
3. проверил бы доступность ресурсов при GET и POST запросе
4. При GET запросе:
    - Проверил бы, что возвращается статус код 200.    
    - Проверил бы, что используется соответствующий шаблон.     
    - Проверил бы, что внутри страницы есть объект формы.    
    - Проверил бы, что форма пустая и без каких то данных.    
    - Если есть ограничение по ролям, проверил бы их. 
    - Проверил бы, авторизован ли пользователь - если есть требование.  
    - Если существует редирект на неавторизованного пользователя - проверил бы  переадресацию.
5. При POST запросе:
    - Проверил бы, типизацию на поля в форме.
    - Проверил бы, что возвращается статус код 201.    
    - Проверил бы, что при отправке формы создается новый объект поста.
    - После того как объект создан, проверил соответствует ли он данным, что были отправлены.
    - Проверил бы, происходит ли редирект.
    - Если у поста есть уникальные поля, проверил бы их на уникальность.
    - Если идет загрузка файла или изображения или видео, то протестировал бы загрузки 