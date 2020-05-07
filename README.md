# Практическое задание.
## Информационная система учебного заведения.

[Ссылка на задание](https://docs.google.com/document/d/1COj5FSznQYb5yC-z6eeu6ggpT8VijWzjwsvZ0ugukN8/edit?usp=drivesdk)

## Структура системы в виде диаграммы классов:

![class diagramm](http://www.plantuml.com/plantuml/img/POv12e0m30JlVKK_q2z8mPFWpHUK6hLGMqWs_rUm5i7ZJdQMU45Ww9bDp474JaMGe4YrDB90LofeQQO8PU8MnweiPCn7izMveLk_GpD-l0-Rfs5TfWsk3xsKqtxSkDSzbVL-_m80)

## Пример исполняемого файла:

```Java
import java.util.*;

class Main {

  public static void main(String[] args) {
    Institution institution = new Institution("Институт", "г. Город");
    
    institution.addCourse(new Course("Физика"));
    institution.addCourse(new Course("Математика"));
    institution.addCourse(new Course("Информатика"));

    institution.addLecturer(new Lecturer("Физик"));
    institution.addLecturer(new Lecturer("Математик"));
    institution.addLecturer(new Lecturer("Информатик Петренко Вениамин Фёдорович"));

    institution.addStudent(new Student("Иванов Иван Иванович"));
    institution.addStudent(new Student("Петров Петр Петрович"));
    institution.addStudent(new Student("Сидоров Сидор Сидорович"));

    for (int i = 1; i < 4; i++) {
      new LecturerForCourseAssigner(institution.getLecturer(i), institution.getCourse(i)).assign();
      new StudentForCourseAssigner(institution.getStudent(1), institution.getCourse(i)).assign();
      new StudentForCourseAssigner(institution.getStudent(2), institution.getCourse(i)).assign();
      new StudentForCourseAssigner(institution.getStudent(3), institution.getCourse(i)).assign();
    }

    Student s = institution.getStudent(1);
    System.out.println();
    System.out.println(s.getName() + " изучает предметы:");
    s.getCourses().forEach(c -> System.out.println(c.getName()));

    System.out.println("\nпредмет " + institution.getCourse(1).getName() + " изучают:\n");
    institution.getCourse(1).getStudents().forEach(st -> System.out.println(st.getName()));
    
    System.out.println("\nпредмет " + institution.getCourse(3).getName() + " ведёт:");
    System.out.println(institution.getCourse(3).getLecturer().getName());
  }

}
```

## [Выполнить программу](https://institution.dmitrysar.repl.run/)
