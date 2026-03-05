## Use Case діаграма (взаємодія користувачів із системою)
```mermaid
flowchart LR

Student[Студент]
Psychologist[Психолог]
Admin[Адміністратор]

System((Система онлайн-запису))

Student -->|реєстрація| System
Student -->|запис на консультацію| System
Student -->|скасування запису| System

Psychologist -->|перегляд розкладу| System
Psychologist -->|проведення консультації| System

Admin -->|керування користувачами| System
Admin -->|налаштування системи| System
```

## Діаграма процесу запису (Flowchart)
```mermaid
flowchart TD

A[Вхід користувача]
B[Перегляд доступних психологів]
C[Вибір дати та часу]
D[Перевірка доступності]
E[Створення запису]
F[Збереження у базі даних]
G[Надсилання підтвердження]

A --> B
B --> C
C --> D
D -->|час вільний| E
D -->|час зайнятий| B
E --> F
F --> G
```

## ER-діаграма бази даних
```mermaid
erDiagram

STUDENT {
string id
string name
string email
}

PSYCHOLOGIST {
string id
string name
string specialization
}

APPOINTMENT {
string id
date appointment_date
string status
}

STUDENT ||--o{ APPOINTMENT : books
PSYCHOLOGIST ||--o{ APPOINTMENT : conducts
```

## Архітектурна діаграма системи
```mermaid
flowchart LR

User[Студент / Психолог]

Web[Веб-інтерфейс]

Server[Сервер застосунку]

DB[(База даних)]

Notification[Система сповіщень]

User --> Web
Web --> Server
Server --> DB
Server --> Notification
```

## Діаграма циклів системи
```mermaid
flowchart LR

A[Реєстрація користувача]
B[Запис на консультацію]
C[Обробка запису]
D[Проведення консультації]
E[Зворотний зв'язок]

A --> B
B --> C
C --> D
D --> E
E --> B
```

## Діаграма точок впливу на систему
```mermaid
flowchart TD

Student[Студент]
Psychologist[Психолог]
Admin[Адміністратор]

Interface[Користувацький інтерфейс]
Logic[Бізнес-логіка]
Database[(База даних)]

Student --> Interface
Psychologist --> Interface
Admin --> Interface

Interface --> Logic
Logic --> Database
Admin --> Database
```