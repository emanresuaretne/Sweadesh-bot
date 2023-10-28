# project-211-emanresuaretne
project-211-emanresuaretne created by GitHub Classroom

Арсений Манусов

Sweadesh bot - проект, направленный на выявление родства языков по сходству их базовой лексики с использованием списков Сводеша. В проекте использовались языки тюркской, славянской, балтской, финской и кельтской языковых групп. Эта тема показалась мне актуальной, т.к. в открытом доступе нет параллельных списков Сводеша для разных языков с перечислением родственных в них слов. Для решения этой проблемы я решил воспользоваться помощью лингвистов и попросил их разметить 1000 строк в написанном мной боте. 

В целом для реализации этого проекта я использовал различные технологии:
1) я написал программу, которая выкачивает данные онлайн словарей на Википедии, чистит их и загружает списки в базу данных. Полученный объем базы 1035 строк разной длины, включающей в себя 5 списков по 207 слов в каждом. (Swadesh_DB) 
2) затем я написал телеграм-бот, который просит пользователей разметить строки из моей базы данных и создал интерфейс, позволяющий сделать это максимально удобно для пользователей. За 5 дней в разметке приняли участие 82 человека (из которых 21 что-то сделали :3), ими было размечено 634 строк (т.е. 62% от исходного числа), которые были загружены в новую базу данных. (Swadesh_bot)
Я не выгружал бот на платформу pythonanywhere, т.к. он предполагался не как финальный проект, а как инструмент на несколько дней, для дальнейшего исследования.
3) следующим шагом я предобработал базу. В ней были слова как на кириллице (например, слова на русском языке), так и слова на латинице (например, на чешском). Я латинизировал все кирилическое, чтобы все унифицировать и упростить дальнейшую работу. Кромк того, я убрал диакритику. Теперь можно было переходить к следующему этапу. 
4) на основе этой обработанной базы (из 635 строк вышло 51676 пар родственных слов) я хотел натренировать нейросеть, которая бы затем сама говорила, является ли пара слов родственной (и, соответственно, языки родственными) или нет. Я перебробовал разные настройки для обучения нейросети, однако лучший результат, который она смогла показать - 74%. Я решил обратиться к другому методу. 
5) Я решил применить взвешенное редакционное расстояние Левенштейна. Оно дало результат значительно выше предыдущего - >82% (Swadesh-analysis)

Я не добился всех поставленных мною задач в условиях сильно сжатых сроков, но т.к. тема интересна для меня, я буду заниматься ею и дальше. В планах получить большую выборку, добавить в бота возможность выкачитвать языковые пары и оценивать для них количество когнатов
