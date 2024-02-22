# Построение блок-схем с помощью mermaid.js

Библиотека [mermaid.js](https://mermaid.js.org/intro/) поддерживается github и позволяет рисовать блок-схемы в разметке `markdown`.

Для VS Code необходимо установить плагины
- Markdown All in One
- Mermaid Markdown Syntax Highlighting
- Markdown Preview Mermaid Support

## Задание направления диаграммы

[Документация Flowcharts](https://mermaid.js.org/syntax/flowchart.html)

### `flowchart TB` (top-bottom == сверху-вниз)

```mermaid
    flowchart TB
    A --> B
```

### `flowchart BT` (bottom-top == снизу вверх)

```mermaid
    flowchart BT
    A --> B
```

### `flowchart LR` (left-right == слева направо)

```mermaid
    flowchart LR
    A --> B
```

### `flowchart RL` (right-left == справа налево)

```mermaid
flowchart RL
A --> B
```

## Задание текста

Текст узла удобно задавать как переменную в квадратных скобках `A[node 1]`.

```mermaid
flowchart LR
    A[node 1] --> B[node 2]
    C[node 3] --> B
```

## Задание формы

Форма задается с помощью скобок разного вида.

```mermaid
flowchart TB
    node1[Форма 1]
    node2(Форма 2)
    node3[(Форма 3)]
    node4([Форма 4])
    node5[[Форма 5]]
    node6((Форма 6))
```

```mermaid
flowchart TB
    node7{Форма 7}
    node8{{Форма 8}}
    node9[/Форма 9/]
    node10(\\Форма 10\\)
    node11[/Форма 11\\]
    node12[\\Форма 12/]
```    

## Вид стрелок

```mermaid
flowchart TB
    A --> B
    C --- D
    E -.-> F
    G ==> H
    I --o J
    K --x L    
```

## Текст на стрелках

```mermaid
flowchart TB
    A-- Text ---B
    C---|Text|D
    E-->|Text|F
    G-- Text -->H
    I-. Text .->J
    K== Text ==>L
```

## Связи схем

```mermaid
flowchart TB
    c1-->a2
    subgraph one
    a1-->a2
    end
    subgraph two
    b1-->b2
    end
    subgraph three
    c1-->c2
    end
```

## Ссылки

```mermaid
flowchart TB
%% комментарий - создаем узел
    A --> B
        click A "https://github.com/experiment0/data_science_helpers" _blank
```

## Стили

- `fill` - заливка
- `stroke` - цвет границы
- `stroke-width` - толщина границы
- `color` - цвет текста
- `stroke-dasharray` - пунктирная граница"
   
```mermaid
flowchart LR
    id1(Start)-->id2(Stop)
    style id1 fill: #564, stroke: #ccc, stroke-width: 4px, color: #fff
    style id2 fill: #ff2400, stroke: #ccc, stroke-width: 4px, color: #fff, stroke-dasharray: 6 6
```

Стили также можно задавать в классах.

```mermaid
flowchart LR
    %% Стили
    classDef class1 fill: #564, stroke: #ccc, stroke-width: 4px, color: #fff
    classDef class2 fill: #ff2400, stroke: #ccc, stroke-width: 4px, color: #fff, stroke-dasharray: 6 6

    %% Диаграмма
    id1(Start):::class1-->id2(Stop):::class2
    id3(Start):::class2-->id4(Stop):::class2
```

## Название
   
```mermaid
---
title: Название диаграммы
---
flowchart LR
    A[Hard edge] -->|Link text| B(Round edge)
    B --> C{Decision}
    C -->|One| D[Result one]
    C -->|Two| E[Result two]
```

## Диаграммы состояний

[Документация State diagrams](https://mermaid.js.org/syntax/stateDiagram.html)
   
```mermaid
---
title: Simple sample
---
stateDiagram-v2
    [*] --> Still
    Still --> [*]

    Still --> Moving
    Moving --> Still
    Moving --> Crash
    Crash --> [*]
```

## Круговые диаграммы

[Документация Pie chart diagrams](https://mermaid.js.org/syntax/pie.html)
    
```mermaid
pie
    "Dogs" : 386
    "Cats" : 85
    "Rats" : 15
```

Возможные темы: forest, default, dark, neutral, base
   
```mermaid
%%{init: {'theme': 'forest'}}%%
pie
    "Dogs" : 386
    "Cats" : 85
    "Rats" : 15
```

Диаграмма с названием

```mermaid
pie title Pets adopted by volunteers
    "Dogs" : 386
    "Cats" : 85
    "Rats" : 15
```

## Диаграммы Ганта

[Документация Gantt diagrams](https://mermaid.js.org/syntax/gantt.html)
   
```mermaid
gantt
    title A Gantt Diagram
    dateFormat YYYY-MM-DD
    section Section
        A task          :a1, 2014-01-01, 30d
        Another task    :after a1, 20d
    section Another
        Task in Another :2014-01-12, 12d
        another task    :24d
```

## Диаграммы классов

[Документация Class diagrams](https://mermaid.js.org/syntax/classDiagram.html)
   
```mermaid
---
title: Animal example
---
classDiagram
    note "From Duck till Zebra"
    Animal <|-- Duck
    note for Duck "can fly\\ncan swim\\ncan dive\\ncan help in debugging"
    Animal <|-- Fish
    Animal <|-- Zebra
    Animal : +int age
    Animal : +String gender
    Animal: +isMammal()
    Animal: +mate()
    class Duck{
        +String beakColor
        +swim()
        +quack()
    }
    class Fish{
        -int sizeInFeet
        -canEat()
    }
    class Zebra{
        +bool is_wild
        +run()
    }
```

## Полезные ссылки

- [Рисуем диаграммы с помощью Mermaid.js и Markdown с Данилом Шатухиным](https://www.youtube.com/watch?v=uJuskThFWW8)