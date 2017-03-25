## Bitcrasher 

Алгоритм заточен на самый жесткий вид сжатия, когда остаётся лишь два цвета: белый фон и чёрный текст. Если вы хотите сохранить приятный вид картинок, то он вам не подходит. Bitcrasher является улучшением утилиты cpaldjvu, которая плохо справляется с неодноцветным фоном (может появиться на сканированном изображении в месте перегиба страницы, например).

### Принцип работы Bitcrasher

В основе лежит идея поиска линейных функций, которые смогут приближать фон. Рассматриваются блоки пикселей и оценивается их возможность принадлежать фону. Для этого используется [метод наименьших моментов][LAD], который подбирает модель для блока пикселей. Ошибки оцениваются с помощью l1 нормы. Метод множителей Лагранжа для поиска экстремума.

### Сравнение с аналогичными алгоритмами:

В левом верхнем углу оригинальное изображение, далее по часовой стрелке: djvulibre, bitcrasher, simpledjvu.

![alt tag](https://github.com/Tehada/Bitcrasher/blob/master/images/compare/11.jpg)


------------ Comments (A.S.) ---------

Конечно, в общем виде такой план достаточно понятен, но если обсуждать подробности, то хорошо бы как-то более подробно описать планы (например, чтобы координировать действия с коллегами). Действительно, использовать имеющуюся тестовую базу правильно, но хорошо бы иметь возможность пробовать разные алгоритмы и разные данные, чтобы получить какие-то более разносторонние оценки. Но, может быть, действительно это уже второй этап, на первом хотелось бы хоть что-то попробовать и посмотреть самому, чтобы зря с самого начала не расстраиваться проигрышами :-)

В общем, мне кажется, что итогом первого этапа могли бы быть

1) собственные алгоритмы с помощью нейронной сети
2) набор изображений разного качества и достаточно разнообразных, не только из DEBCO, но и вообще (потому что, скажем, печатные тексты сильно отличаются от ку
3) обзор, какие алгоритмы существуют и
4) сравнительные результаты тестирования.

Вопрос о встраивании этого в djvulibre и вообще тогда можно пока (ненадолго :-) отложить...

Программы Межирова: https://gitlab.com/alih/turbinarize.git

https://jwilk.net/software/didjvu 

minidjvu (sourceforge)

Польские коллеги:

http://bc.klf.uw.edu.pl/298/6/JSBatal_Library-12s.pdf
https://jwilk.net/software/didjvu и др.

----

Возможные альтернативы:

* Улучшения k-means clustering, который встроен в djvulibre

* expectation-maximization algorithm -- 

* k-nearest neighbor classifier -- machine learning algorithm (Rocchio algorythm).



[LAD]: https://ru.wikipedia.org/wiki/%D0%9C%D0%B5%D1%82%D0%BE%D0%B4_%D0%BD%D0%B0%D0%B8%D0%BC%D0%B5%D0%BD%D1%8C%D1%88%D0%B8%D1%85_%D0%BC%D0%BE%D0%B4%D1%83%D0%BB%D0%B5%D0%B9

[FGKA]: https://www.ncbi.nlm.nih.gov/pmc/articles/PMC543472/
