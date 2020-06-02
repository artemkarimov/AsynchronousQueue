Асинхронная очередь на JavaScript

Очередь реализована на классе.

С помощью метода push() в её экземпляр добавляются элементы.
В экземпляр очереди приходят данные о пользователе (объект с тремя ключами: пользователь, компания, приоритет)
и массив заданий каждого пользователя.

В языке программирования JavaScript уже появились приватные методы классов (которые начинаются с #). 
Моя версия Node.js даже после обновления их ёще не поддерживает. 
Методы, которые были бы приватными, начинаются с _.

При использовании метода prioritise() задания пользователей расставляются по приоритету.

Метод setFactors() выясняет, есть ли в очереди факторы. Факторами очереди становятся пользователи,
если их компании переданы в аргумент этого метода, если же аргумент не передаётся,
то используется значение по умолчанию. Если факторы есть, то их задания ставятся на начало очереди,
невзирая на приоритет. Все остальные задания исполняются либо по приоритету, либо, если он не был вызван,
в том порядке, в котором они пришли в очередь.

Метод  init() заполняет (строит) очередь в зависимости от того, используются ли приоритеты, есть ли факторы.

Метод start() асинхронный. Написан с помощью async/await. Он возвращает промисы, и только в том случае,
если в очередь были доданы данные методом push(), и очередь была сформирована методом init().
