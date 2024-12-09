# Коллекция вопросов к собеседованию
В этом репозитории собраны различные вопросы, которые попадались мне на собеседованиях на позицию _Java Backend Developer_.
Автор - Фёдор Гусев
Telegram - [@blacklosh](https://t.me/blacklosh)
Почта - blacklosh@bk.ru

## Раздел "Алгоритмы и Структуры данных"
### Что такое O() нотация? Для чего она применяется?
Нотация большого О() применяется для асимптоматической оценки временной сложности или сложности по памяти в зависимости от входных параметров. В качестве аргумента функции может выступать:
* O(1) - константная сложность. Означает, что сложность не зависит от количества входных параметров. Это не означает, что алгоритм всегда выполнится ровно за 1 секунду, это лишь означает, что он будет работать одинаковое время на любых данных. Если говорим про память, то это означает, что он всегда расходует фиксированное количество памяти.
* О(logN) - логарифмическая сложность. Означает, что для обработки N данных потребуется logN времени или logN памяти. Опять же, перед логарифмом может быть любая константа.
* О(N), O(N^2), ... - полиномиальная сложность. Частные случаи: O(N) - линейная сложность. Сколько входных данных, столько времени или памяти потребуется; O(N^2) - квадратичная зависимость и так далее.
* O(2^N) - экспоненциальная сложность. Худшая сложность, достигается на алгоритмах полного перебора.

Сложности могут образовывать достаточно сложные объединения, например:
* O(N*logN) - типичная скорость многих сортировок;
* O(N^2 * M)

При сложении нескольких параметров в О() нотации остаётся только самый весомый, т.е. O(N^2 + N) = O(N^2).

Важно понимать, что при оценке памяти алгоритма не участвует уже выделенная память под хранение данных. Например, для линейного поиска в массиве сложность будет О(1), а не О(N), несмотря на то, что под хранение массива нужно N памяти.

### Назовите основные сортировки, их скорости в лучшем, среднем, худшем случае
![Ответ](https://habrastorage.org/r/w1560/getpro/habr/post_images/b91/1bc/ca9/b911bcca9ca9f9d8b0fa781a49118553.png)

### Назовите основные структуры для хранения данных, их упорядоченность, скорость операций
![Ответ](https://habrastorage.org/getpro/habr/post_images/9a5/f72/788/9a5f72788d9e0e5ac0d0e585e3b3632f.png)

## Раздел "Java Core"
### Почему java кросплатформенная? Объясните слоган java: "напишите единожды, используйте везде"

### Объясните, что такое **JRE**, **JVM**, **JDK**

### Расскажите, что такое опции виртуальной машины. В чём разница **Xms**, **Xmx**, **Xss**

### Назовите как можно больше побитовых операций
* ~X
* X & Y
* X | Y
* X ^ Y
* X >> Y
* X << Y
* X >>> Y

### Любой ли объект может быть передан в **try-with-resourses**?
Нет, только реализующий интерфейс __Closable__

### Что такое **stack trace**?
### Что такое POJO?

### Перечислите методы класса **Object** 
* toString 
* equals
* hashCode
* wait
* notify
* notifyAll
* clone
* finilize
* getClass

### Что такое __imutable__ класс? Как его создать?
Для создания неизменяемого класса необходимо:
* Объявить класс как final, чтобы его нельзя было расширить и подклассы не могли переопределить методы;
* Сделать все поля private, чтобы прямой доступ был запрещён;
* Сделать все поля final, чтобы значение нельзя было изменить после инициализации;
* Не предоставлять методы setter для переменных;
* Инициализировать все поля с помощью метода конструктора, выполняющего глубокое копирование;
* Выполнить клонирование объектов в методах getter, чтобы возвращать копию, а не реальную ссылку на объект.

### В чём разница сравнения по == и по equals?

### Что такое переопределение и перегрузка?

### Какими способами можно сконструировать объект в Java?

### Что такое сигнатура метода? Что в неё входит?
В сигнатуру метода входит название и аргументы, не входит возвращаемое значение, тело, исключения.

### В чём отличие абстрактного класса от интерфейса?
Абстрактный класс может представлять не только поведение (методы), но и состояние (переменные).

### Зачем нужны классы-обёртки? Что такое Boxing, Unboxing?

### Как происходит передача ссылочного типа в аргумент метода?

### Расскажите про JMM. Работа нескольких потоков с памятью, сборщики мусора

### Строки - В чём разница инициализации через строковый литерал и через new?

### Расскажите про String pool, метод intern()

### Объясните минусы конкатенации через +

### StringBuilder, StringBuffer, их различия

### В какой кодировке хранятся строки? 
Зависит от версии java

### Почему хранить пароль предпочтительнее в char[]/byte[], а не в String?

### Расскажите про default методы интерфейса

### Реализация нескольких интерфейсов

### Throwable - это класс или интерфейс?
Класс, как ни странно

### Что такое раннее и позднее связывание?

### Что такое Upcast?

### Расположите в порядке строгости модификаторы доступа
* private
* default(package-private)
* protected
* public

### Особенности модификаторов
* Какие возможны для поля? (все)
* Какие возможны для метода? (все)
* Какие возможны для класса? (только default и public для внешних классов, + private для внутренних)

### Что даёт модификатор static для поля? метода? класса?

### Что даёт модификатор final для поля? метода? класса?

### Можно ли перегрузить конструктор? а переопределить?

### Всегда ли вызывается родительский конструктор? 
Да, неявно

### Чем отличается конструктор от метода?

### Можно ли this присвоить null? 
Нет

### Когда исчезает аннотация? 
Retention (runtime, class, source)

### На что может быть навешена аннотация? 
Target (Type, Method, Field)

### Что такое маркерная аннотация?

## Enum
* Какие плюсы? память
* Как добавить поля, конструктор?
* Область видимости (всегда public)
* Enum как ключ map (EnumMap class)

## Collections
* Что такое collection? Интерфейс
* iterable и iterator
* Иерархия collection
![Ответ](https://viettuts.vn/images/java/java-collection/he-thong-cap-bac-colection-trong-java.png)
* Stack - это класс или интерфейс? класс
* Queue и deque

### HashMap
* В чём отличие HashMap от HashTable (возможность использовать один ключ null, блокировка не всей таблицы, а только бакета при обращении)
* Контракт equals и hashCode, как HashMap проверяет наличие объекта
* Привести пример плохой реализации hashCode()
* Отличие hashMap от treeMap
* Алгоритмические сложности HashMap (~O(1))
* Как устроен hashSet? Тупо внутри hashMap, но значение всегда null
* Что будет, если попытаться вставить в HashMap уже имеющийся в ней ключевой объект? замена
* Случай, когда можем положить объект в мапу, а потом не можем найти (изменился хеш ключа) (нельзя так делать!)
* !!! ConcurrentHashMap
* Как отсортировать по значению? Через stream sort в linkedHashMap

### TreeMap
* Сложность O(log(N))
* Внутренняя реализация (красно-чёрное дерево)
* Можно ли хранить null? нет
* Можно ли хранить разные классы? нет
* Условия использования (наличие Comparator / Comparable)

### List
* Отличие arrayList от linkedList, алгоритмические сложности
* Вставка в середину arrayList
* Расширение arrayList

## Многопоточка
* wait, notify, notifyAll
* synchronized
* !!! JMM
* Callable, Runnable и Thread
* Жизненный цикл потока
* Daemon потоки
* Thread pool (зачем? переиспользовать потоки, убивать дорого)
* Интерфейсы Executor и ExecutorService
* !!! Утечки памяти
* !!! volatile
* Атомарные типы данных, обёртки

## Stream API
* Что такое стримы? Как работают? К чему применяются? Откуда лямбды? Функциональщина
* Типы операций: конвейерные, терминальные
* Filter, Map, FlatMap, Peek, Sorted
* collect, forEach, count, reduce, findFirst, anyMatch
* Коллекторы
* Optional

## Generics
* Diamond operator
* Ковариантность: <? extends T>
* Wildcard <?> то же самое <? extends Object>
* Контрвариантность: <? super T>
* Инвариатность: < T >
* Есть ли generics в runtime? (нет, т.к. обратная совместимость)
* Кто разбирается с правильностью операций? Compiler

## Exceptions
* Иерархия исключений
![Ответ](https://fuzeservers.ru/wp-content/uploads/e/f/7/ef79d4a747c25ed5d44c345f6d5bcfde.png)
* Проверяемые, непроверяемые
* try/catch, multi-catch, несколько catch подряд
* throw и throws

## Тесты
* JUnit, принцип работы
* @Test, @Before, @After, @BeforeAll, @AfterAll
* assert, assertThat, assertEquals, fail

## Сериализация и десериализация
* Как пометить переменную, которая не должна сериализоваться - @Transient

## IO
* Reader/Writer, надстройки

## Три(или четыре) кита ооп
* Инкапсуляция
* Наследование (сколько может быть родителей? а как реализовать множественное наследование? восходящее и нисходящее преобразования)
* Полиморфизм: один интерфейс - множество реализаций
* Абстракция
* Я являюсь и я имею

## SOLID
* Single Responsibility (не делай god object)
* Open-closed
* Liskov substitution
* Interface segregation
* dependency injection

## Другие принципы хорошего кода
* KISS (keep it simple, stupid)
* DRY (dont repeat yourself)
* YAGNI (You Aren’t Gonna Need It)

# Spring Framework
* Что такое IoC контейнер, DI?

## Bean
* Что такое бин? xml объявление, @Bean, @Component, @ComponentScan
* Инжект @Autowired, через конструктор
* Циклическая зависимость бинов BeanCurrentlyInCreationException, как избежать? архитектура / lazy / не через конструктор(сеттер)

## Конктекст
* Configuration

## Scope
* Что такое scope? область жизни бина
* Основные scopes: singleton (по умолчанию), prototype, request, session, application, websocket

## Паттерны проектирования
* Builder
* Factory method, factory, abstract factory
* Proxy
* MVC
* Service locator
* Singletone

## Transactional

## AOP
* Зачем?
* Aspect, join point, pointcut, advice
* !!! Либы, отвечающие за это

## SpringBoot
* Автоконфигурация
* Стартеры

## Выполнение запросов
* Dispatcher servlet, определение контроллера, контроллер, view resolver, view
* filters, filterChain

## Spring security
* User, UserDetails, UserDetailsService
* Где может храниться пользователь
* Роли
* PasswordEncoder
* authorizeRequests
* фильтры: login, csrf, cors, logout, anonymous
* globalMethodSecurity: pre/postAuthorize
* SecurityContextHolder

# Hibernate
* Что такое ORM? JPA?
* Основные аннотации
* Object pool
* Связи
* проблемы Lazy/Eager для list
* проблема N+1 запроса

# SQL
* Синтаксис, назначение
* ACID
* having и where
* что такое индекс?
* group by

# REST
* Соглашение о путях
* Статус коды (200, 201, 202, 302, 400, 401, 403, 404, 405, 415, 500)
* Методы
* Отличия post/put/patch
* Как отделяется тело запроса?
* Зачем нужен заголовок host?
* Можно ли отправить тело запроса GET?
* Как отправляется форма? url-form-encoded
* json
* jwt, никаких сессий

# Инструменты
* Docker, Dockerfile, Docker Compose
* Kubernetes, OpenShift, Docker Swarm
* Grafana
* ELK stack (ElasticSearch, Logstash, Kibana)
* Prometheus

# Вопросы со звёздочкой
* Когда не выполнится finally? (System.exit, Error, while(true), не return!)
* Поддерживает ли язык Java множественное наследование? Java поддерживает множественное наследование типов, ведь интерфейс в нём может расширять другие интерфейсы. Но множественное наследование реализаций язык Java не поддерживает.
* 1.0/0.0 = Double.INFINITY
* Можно ли использовать return в конструкторе? да, но без возвращаемого значения
* Можно ли из конструктора бросить исключение? да
* Можно ли в конструкторе вызвать другой конструктор? да, this(). А несколько? нет. А не первой строчкой? нет
* Где лежат поля-примитивы у классов? на heap
* Finilize / finally / final?
* В чём отличие инициализации констант в конструкторе и при объявлении? время срабатывания
* Можно ли сделать static метод final ? да
* Что получим в int a = Integer.MAX_VALUE + 10;
* Скомпилится ли byte b1 = 1 + 3;
* Тип данных больше long (BigInteger)
* Может ли метод быть статическим и абстрактным одновременно? нет
* Можно ли использовать из статического метода нестатический? нет
* Может ли интерфейс быть final? нет
* Как сделать класс, экземпляр которого нельзя создать? private конструктор
* Можно ли в java сделать pointers? ссылки, как в cpp? нет
