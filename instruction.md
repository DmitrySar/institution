# Диаграмма классов.

Диаграмма классов отображает структуру информационной системы.
Элементами диаграммы являются классы, а также стрелки, показывающие взаимодействие между классами.
Класс - это множество объектов с одинаковым списком свойств или параметров.
Например, класс стол может включать в себя такие параметры, как высота, количество ножек, материал из которого он изготовлен и т.д.
Диаграмма классов помогает построить модель системы до написания программы.


Разберём классы Student и Institution.
Эти классы будут обладать определёнными свойствами, а также взаимодействовать друг с другом.
Тип отношения, когда один класс включает в себя другой класс, но эти классы могут существовать независимо друг от друга называется **агрегацией**, обозначается на схеме такой стрелкой:
![Агрегация](http://www.plantuml.com/plantuml/img/SoWkIImgAStDuIh9BCb9LRWmuSBcYmqNjbxOV673nROBEoxsSt5vvXK39KjBClFp5F9rYpBJCqfq5O9BIbDIyqguk1nIyrA0-W40)

Далее, у студента должно быть имя, и лучше передавать его сразу в конструктор. Должен быть какой-то номер, чтобы не путать студентов с одинаковыми именами, должен быть список предметов, изучаемых студентом. Соответственно должны быть методы для добавления курса, метод получения номера, получения имени, получения списка предметов.
Т.о. мы получаем диаграмму класса Student:

![Student](http://www.plantuml.com/plantuml/img/SoWkIImgAStDuKhEIImkLWWkAKr9pIjHgERYqbN8JB5IoCmh0RBo4dDJhO2IHPbvwK1kSdvfKN5giPM2JsPnYOqpc6V7nQKDqww1h5uJA9wUMk875DBGX1i25eFeB0O9evW4blHC0Oc3xEUgvUBYSaZDIm6w4m00)

По этой диаграмме уже можно создать класс на языке Java:

```Java
//импорт класса ArrayList
import java.util.ArrayList;

class Student {
  
  private static int count = 0;//количество студентов
  private int id;//номер студента
  private final String name;//имя студента
  private ArrayList<Course> courses = new ArrayList<>();//список предметов
  
  //конструктор класса
  public Student(String name) {
    this.id = ++count;//увеличиваем количество на 1, задаём номер студента
    this.name = name;//задаём имя студента
  }
  
  //метод возврата номера студента
  public int getId() {
    return this.id;
  }
  
  //метод возврата имени студента
  public String getName() {
    return name;
  }
  
  //метод добавления предмета изучения
  public void addCourse(Course course) {
    courses.add(course);
  }
  
  //метод получения списка изучаемых предметов
  public ArrayList<Course> getCourses() {
    return courses;
  }
  
}
```

По аналогии создаются другие классы в проекте.
