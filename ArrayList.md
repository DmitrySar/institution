# Как работать со списком ArrayList.

Есть список объектов типа Student, наша задача научиться помещать объекты в список, извлекать объекты с определёнными свойствами.

Создание пустого списка, с названием students, объектов Student:
```Java
ArrayList<Student> students = new ArrayList<>();
```

Добавление нового объекта типа Student:

```Java
students.add(new Student("Иванов Иван Иванович");
```
Метод для добавления объекта Student:
```Java
public void addStudent(Student student) {
  students.add(student);
}
```

Метод для получения объекта Student:

```Java
public Student getStudent(int id) {
  return students.stream().filter(s -> s.getId() == id).findFirst().get();
}
```

Здесь:
- **stream()** - получение потока;
- **filter()** - выборка из потока, по определённому условию;
  - **(s -> s.getId() == id)** - условие выборки в виде лямбда-выражения;
- **findFirst()** - нахождение первого совпадения по условию;
- **get()** - получение результата.
