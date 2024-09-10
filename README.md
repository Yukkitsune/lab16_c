Часть 1
Реализовать шаблон для задания «умного» указателя по аналогии шаблона
std::unique_ptr. В шаблоне предусмотреть конструктор, который получает «сырой»
указатель, деструктор, конструкторы копирования и перемещения (что-то удаляется),
операторы присваивания с копированием и перемещением (что-то удаляется), метод get,
возвращающий «сырой указатель», выполнить перегрузку операций * и ->, запретить
создание копий объектов, реализовать перемещение. Возможные заголовки методов
шаблона кроме конструкторов и операторов присваивания копирования и перемещения
приведены ниже:
template<class T>
class MyUnique
{
 T * p=nullptr;
public:
 MyUnique(T *p);
 ~MyUnique();
 T * get() const;
 T & operator*();
 T * operator->();
};
Для создания объекта типа MyUnique разработать глобальную шаблонную функцию
Make_MyUnique с переменным числом параметров, которая получает параметры как у
конструктора объекта, на который указывает указатель. Теория по таким функциям
приведена ниже в подразделе Шаблоны с переменным числом параметров (variadic
template).
В функции main продемонстрировать все заданные возможности, в том числе,
создать указатель на объект своего класса, имеющего конструктор с параметрами
(например, класса MyPoint – точка на плоскости) c помощью функции Make_MyUnique,
получающей параметры как конструктора своего класса (MyPoint).
Часть 2
Аналогично разработать шаблон для задания «умного» указателя по аналогии
шаблона std::shared_ptr, который отличается от шаблона части 1 тем, что разрешает
копирование. Назвать его можно MyShared. Разработать также глобальную шаблонную
функцию Make_MyShared, которая получает параметры как у конструктора объекта, на
который указывает указатель. Продемонстрировать все возможности в функции main по
аналогии с частью 1.
