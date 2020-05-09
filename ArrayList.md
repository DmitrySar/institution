# Как работать со списком [ArrayList](https://metanit.com/java/tutorial/5.2.php).

Есть список объектов типа Student, наша задача научиться помещать объекты в список, извлекать объекты с определёнными свойствами.

Создание пустого списка, с названием students, объектов Student:
```Java
ArrayList<Student> students = new ArrayList<>();
```

Добавление нового объекта типа Student:

```Java
students.add(new Student("Иванов Иван Иванович"));
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
- **stream()** - получение [потока данных](https://metanit.com/java/tutorial/10.1.php);
- **filter()** - [выборка из потока, по определённому условию](https://metanit.com/java/tutorial/10.3.php);
  - **(s -> s.getId() == id)** - условие выборки в виде [лямбда-выражения](https://metanit.com/java/tutorial/9.1.php);
- **findFirst()** - [нахождение первого совпадения по условию](https://metanit.com/java/tutorial/10.11.php);
- **get()** - [получение результата](https://metanit.com/java/tutorial/10.12.php).
