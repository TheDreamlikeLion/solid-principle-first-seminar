## Домашнее задание 6.

При анализе кода замечены следующие нарушения принципов SOLID:
1. В классе User написаны методы report и save. Это нарушает принцип Single Responsibility Principle.
   Стоит вынести эти методы в отдельные классы или в общий класс, отвечающий за действия с User'ом.
2. Так же стоит поступить с классом Main, в котором происходит много действий, а не одно - запуск приложения.
3. В методе save класса User создается new Persister. Зависимость классов ничем не обоснована, логически ниоткуда не вытекает. Это нарушает принцип Dependency Inversion Principle.
   Стоит оба класса сделать наследниками абстрактных классов.
4. Поскольку методы save есть как в классе User, так и в классе Persister, стоит выделить эти методы в отдельных интерфейсах. Это позволит соответствовать принципу Interface Segregation Principle.
5. Так же стоит поступить с методом report, выделив его в отдельный интерфейс или класс.

(6. Как я понял, Persister - это название постоянного реестра, куда должна сохраняться запись о новом экземпляре класса User.
   Тогда по такой же логике должен быть сделан метод для иных действий с записями экземпляров User. Например, read, update.)
