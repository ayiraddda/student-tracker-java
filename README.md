# student-tracker-java
Console based student tracker
# Student Tracker — Java
Консольное приложение для управления успеваемостью студентов
Язык: **Java (Core)** | Интерфейс: **CLI** | Данные: **in-memory (List + HashMap)**
## Структура проекта
src/
├── model/
│   ├── Student.java      # Сущность студента
│   ├── Course.java       # Сущность предмета
│   └── Grade.java        # Связь студент – предмет – оценка
├── service/
│   └── TrackerService.java  # Вся бизнес-логика и аналитика
└── main/
    └── Main.java         # Консольное меню (точка входа)
```

## Как запустить

### Через командную строку

```bash
# 1. Перейдите в папку src
cd src

# 2. Скомпилируйте все файлы
javac model/Student.java model/Course.java model/Grade.java \
      service/TrackerService.java main/Main.java

# 3. Запустите
java main.Main
```

### Через IntelliJ IDEA

1. File → Open → выберите папку `student-tracker`
2. Отметьте `src` как **Sources Root** (правой кнопкой → Mark Directory as → Sources Root)
3. Откройте `main/Main.java` и нажмите зелёную кнопку Run

---

## Возможности

| Пункт меню | Описание |
|---|---|
| 1. Add student | Добавить студента (ID, имя, группа) |
| 2. Add course | Добавить предмет (код, название) |
| 3. Assign grade | Выставить оценку (0–100) |
| 4. Show student GPA | Средний балл студента + детали |
| 5. Show top-3 students | Топ-3 по успеваемости |
| 6. Course analytics | Средний балл по каждому предмету |
| 7. Students above threshold | Студенты выше заданного GPA |
| 0. Exit | Выход |

---

## Валидация

- Оценка строго от **0 до 100** — иначе выводится ошибка
- Несуществующий `studentId` — сообщение, программа не падает
- Некорректный ввод числа — `NumberFormatException` перехватывается
- Дублирующийся ID студента или код предмета — сообщение об ошибке
