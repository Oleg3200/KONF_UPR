# Практическая №3.

# Задание 1
``` jsonnet
local groupTemplate(index) = "ИКБО-" + index + "-20";

local groups = [groupTemplate(i) for i in std.range(1, 24)];

local studentTemplate(name, age, group) = {
  age: age,
  group: group,
  name: name,
};

local students = [
  studentTemplate("Полянский М.Д.", 18, "ИКБО-6-20"),
  studentTemplate("Мамедов И.Н.", 18, "ИКБО-7-20"),
  studentTemplate("Синицын О.И.", 19, "ИКБО-4-20"),
  studentTemplate("Пасечкин И.А.", 19, "ИКБО-10-20"),
];

{
  groups: groups,
  students: students,
  subject: "Конфигурационное управление",
}
```
``` json
{
  "groups": [
    "ИКБО-1-20",
    "ИКБО-2-20",
    "ИКБО-3-20",
    "ИКБО-4-20",
    "ИКБО-5-20",
    "ИКБО-6-20",
    "ИКБО-7-20",
    "ИКБО-8-20",
    "ИКБО-9-20",
    "ИКБО-10-20",
    "ИКБО-11-20",
    "ИКБО-12-20",
    "ИКБО-13-20",
    "ИКБО-14-20",
    "ИКБО-15-20",
    "ИКБО-16-20",
    "ИКБО-17-20",
    "ИКБО-18-20",
    "ИКБО-19-20",
    "ИКБО-20-20",
    "ИКБО-21-20",
    "ИКБО-22-20",
    "ИКБО-23-20",
    "ИКБО-24-20"
  ],
  "students": [
    {
      "age": 18,
      "group": "ИКБО-6-20",
      "name": "Полянский М.Д."
    },
    {
      "age": 18,
      "group": "ИКБО-7-20",
      "name": "Мамедов И.Н."
    },
    {
      "age": 19,
      "group": "ИКБО-4-20",
      "name": "Синицын О.И."
    },
    {
      "age": 19,
      "group": "ИКБО-10-23",
      "name": "Пасечкин И.А."
    }
  ],
  "subject": "Конфигурационное управление"
}
```
![image](https://github.com/user-attachments/assets/c6c5686c-96e9-41dc-bfc8-97f1157dacb9)
![image](https://github.com/user-attachments/assets/9db288a8-59fd-42fc-ae5f-c1c6913930fd)



# Задание 2

```
let Group = List Text

let Student = { age : Natural, group : Text, name : Text }

let groups : Group =
      [ "ИКБО-1-20"
      , "ИКБО-2-20"
      , "ИКБО-3-20"
      , "ИКБО-4-20"
      , "ИКБО-5-20"
      , "ИКБО-6-20"
      , "ИКБО-7-20"
      , "ИКБО-8-20"
      , "ИКБО-9-20"
      , "ИКБО-10-20"
      , "ИКБО-11-20"
      , "ИКБО-12-20"
      , "ИКБО-13-20"
      , "ИКБО-14-20"
      , "ИКБО-15-20"
      , "ИКБО-16-20"
      , "ИКБО-17-20"
      , "ИКБО-18-20"
      , "ИКБО-19-20"
      , "ИКБО-20-20"
      , "ИКБО-21-20"
      , "ИКБО-22-20"
      , "ИКБО-23-20"
      , "ИКБО-24-20"
      ]

let students : List Student =
    [ { age = 18, group = "ИКБО-6-20", name = "Полянский М.Д." }
    , { age = 18, group = "ИКБО-7-20", name = "Мамедов И.Н." }
    , { age = 19, group = "ИКБО-4-20", name = "Синицын О.И." }
    , { age = 19, group = "ИКБО-10-20", name = "Пасечкин И.А." }
    ]

in
  { groups = groups
  , students = students
  , subject = "Конфигурационное управление"
  }
```

```
groups:
  - "ИКБО-1-20"
  - "ИКБО-2-20"
  - "ИКБО-3-20"
  - "ИКБО-4-20"
  - "ИКБО-5-20"
  - "ИКБО-6-20"
  - "ИКБО-7-20"
  - "ИКБО-8-20"
  - "ИКБО-9-20"
  - "ИКБО-10-20"
  - "ИКБО-11-20"
  - "ИКБО-12-20"
  - "ИКБО-13-20"
  - "ИКБО-14-20"
  - "ИКБО-15-20"
  - "ИКБО-16-20"
  - "ИКБО-17-20"
  - "ИКБО-18-20"
  - "ИКБО-19-20"
  - "ИКБО-20-20"
  - "ИКБО-21-20"
  - "ИКБО-22-20"
  - "ИКБО-23-20"
  - "ИКБО-24-20"
students:
  - age: 18
    group: "ИКБО-6-20"
    name: "Полянский М.Д."
  - age: 18
    group: "ИКБО-7-20"
    name: "Мамедов И.Н."
  - age: 19
    group: "ИКБО-4-20"
    name: "Синицын О.И."
  - age: 19
    group: "ИКБО-10-20"
    name: "Пасечкин И.А."
subject: "Конфигурационное управление"
```
![image](https://github.com/user-attachments/assets/31f34ce9-8102-4ba0-8e8a-5c93dd1fa073)
![image](https://github.com/user-attachments/assets/5d85e38b-3d6a-42ee-845c-e16b72a58cf0)
![image](https://github.com/user-attachments/assets/4bb31e36-8ab9-4fe8-b679-a5845afbea0e)


# Задание 3 

```
BNF = '''
S = A | B | C | D | E
A = 1 | 1 A | 1 B
B = 0 | 0 B
C = 1 1
D = 1 0 1 1 0 1
E = 0 0 0
'''

for i in range(10):
    print(generate_phrase(parse_bnf(BNF), 'S'))
```
![image](https://github.com/user-attachments/assets/a4a3d29b-bdd4-459b-8c6f-7d50f917d9e1)


# Задание 4

```
BNF = '''
S = A | B | C
A = ( S ) | { S } | ε
B = ( A ) | { A }
C = ε
'''

for i in range(10):
    print(generate_phrase(parse_bnf(BNF), 'S'))

```
![image](https://github.com/user-attachments/assets/c652465c-404f-48c9-8fc1-07a7bf869d23)


# Задание 5

```
BNF = '''
S = E
E = E & T | E | T
T = T | F | ~T | ( E )
F = x | y
'''

for i in range(10):
    print(generate_phrase(parse_bnf(BNF), 'S'))
```
![image](https://github.com/user-attachments/assets/3dc93b61-4a32-4526-8b3e-1cc574171c6b)



