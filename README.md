SearchEngine
Проект SearchEngine представляет собой систему поиска предложенных фраз на определенном сайте (группе сайтов). Программа индексирует страницы сайтов и сохраняет в базу данных имеющиеся на их страницах леммы. На вкладке статистики можно видеть, сколько проиндексировано сайтов и страниц, а также общее количество лемм.

После этого при введении текстового запроса пользователь получает список страниц, содержащих составляющие его слова, начиная с наиболее релевантных (где предложенных в запросе слов больше всего).
В результате поиска указывается число страниц, соответствующих запросу.

При желании пользователь может проиндексировать отдельную страницу, принадлежающую одному из указанных в конфигурационном файле сайтов.
Это можно сделать как до полной индексации сайта, так и после - с целью обновления данных.

Также имеется возможность осуществлять поиск как по полному списку проиндексированных сайтов, так и по конкретному сайту.

_____В проекте задействованы технологии Java, Spring, Hibernate, MySQL, JavaScript._____
Перед запуском проекта
1. следует создать на локальном сервере SQL базу данных с названием search_engine,
задав characterset utf8mb4 и collation utf8mb4_0900_as_ci,
2. в файле application.yaml указать данные для доступа к серверу,
username: root
password: 1234
url: jdbc:mysql://localhost:3306

а также адреса и имена сайтов для индексации и поиска:


при желании можно изменить размер сниппета
(фрагмента текста, который будет представлен в результатах поиска) 

данные для доступа к серверу нужно указать и в файле META-INF/persistence.xml (в двух блоках):


Для начала работы с приложением
нужно запустить файл SearchEngine.jar, например, с помощью командной строки: java -jar SearchEngine.jar
После этого интерфейс программы будет доступен в браузере по адресу http://localhost:8080/
Программа откроется на вкладке статистики: DASHBOARD
Разумеется, если база данных search_engine пуста, на всех кнопках будет отображаться нулевое количество.


Нажав на имя любого из сайтов можно получить более подробную информацию: 

На вкладке MANAGEMENT можно запустить индексацию всех указанных в конфигурационном файле сайтов,
нажав на кнопку START INDEXING. 

Или ввести адрес отдельной страницы, относящейся к одному из этих сайтов, и нажать ADD/UPDATE 

В случае, если страница недоступна или не существует, отразится соответствующее сообщение.
Аналогично будут отображаться и сообщения об ошибках ввода, индексации или поиска. 

Для поиска по проиндексированным страницам нужно перейти на вкладку SEARCH
Искать можно как сразу по всем сайтам: 

так и по выбранному в выпадающем списке: 
