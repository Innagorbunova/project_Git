По заказу «Бета-Банка» мы создали системы, способные на основе анализа поведения клиентов спрогнозировать их отток из банка, путем построения моделей машинного обучения типов "Случайный лес", "Дерево решений" и "Логистическая регрессия". По условию заказчика метрикой качества модели должна являться F1-мера со значением не менее 0.59.

Модели построены на основе данных «Бета-Банка», разделенных на учебную, валидационную и тестовую выборки, на которых модели соответственно были созданы и обучены, проверены и протестированы. В исходном датасете и на всех выборках имелся дисбаланс классов: число объектов отрицательного класса в четыре раза превышало число объектов положительного класса.

Ни в одной из моделей ("Случайный лес", "Дерево решений", "Логистическая регрессия"),  построенных при дисбалансе классов, F1-мера не достигла заданного условием проекта значения (0.59).

Для устранения дисбаланса классов к каждой из трех моделей (с установленными лучшими гиперпараметрами) были применены методы взвешивания классов аргументом class\_weight, увеличения количества объектов положительного класса техникой upsampling и уменьшения числа объектов отрицательного класса техникой downsampling, что привело к увеличение значений F1-меры и AUC ROC по сравнению с несбалансированными данными.

Для модели "Случайный лес" методами, повысившими F1-меру до необходимого значения (0.59), явились взвешивание классов и увеличение выборки. Иным моделям не удалось достичь F1-меры, позволяющей принять их во внимание.

Моделью, отвечающей условию проекта стал "Случайный лес", созданный при увеличении количества объектов положительного класса, показавший (на тесте с гиперпараметрами n\_estimators = 31, max\_depth = 11, min\_samples\_leaf = 2) F1-меру = 0.64, AUC ROC: 0.87 и количество ложноотрицательных ответов -118.
