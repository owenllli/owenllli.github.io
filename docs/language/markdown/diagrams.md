# Diagrams 图表

图表可以帮助传达不同技术组件之间复杂的关系和相互连接，是项目文档的极佳补充。Material for MkDocs 集成了 Mermaid.js，这是一个非常流行且灵活的绘图工具。下面的使用方法也都是基于 Mermaid 的语法进行的，Mermain的教程可以[在此处查看](https://mermaid.js.org/ecosystem/tutorials.html)。
TODO:学会怎么使用Mermaid画图

## 使用方法

### 流程图(Flowcharts)

流程图用于表示工作流或过程。步骤会以各种节点形式呈现，并通过边连接，描述步骤的执行顺序。

```` markdown title="流程图"
``` mermaid
graph LR
  A[Start] --> B{Error?};
  B -->|Yes| C[Hmm...];
  C --> D[Debug];
  D --> B;
  B ---->|No| E[Yay!];
```
````

``` mermaid
graph LR
  A[Start] --> B{Error?};
  B -->|Yes| C[Hmm...];
  C --> D[Debug];
  D --> B;
  B ---->|No| E[Yay!];
```

### 序列图(Sequence Diagrams)

序列图描述了多个对象或参与者之间的交互顺序，以及它们之间的信息交换。

```` markdown title="序列图"
``` mermaid
sequenceDiagram
  autonumber
  Alice->>John: Hello John, how are you?
  loop Healthcheck
      John->>John: Fight against hypochondria
  end
  Note right of John: Rational thoughts!
  John-->>Alice: Great!
  John->>Bob: How about you?
  Bob-->>John: Jolly good!
```
````

``` mermaid
sequenceDiagram
  autonumber
  Alice->>John: Hello John, how are you?
  loop Healthcheck
      John->>John: Fight against hypochondria
  end
  Note right of John: Rational thoughts!
  John-->>Alice: Great!
  John->>Bob: How about you?
  Bob-->>John: Jolly good!
```

### 状态图(State Diagrams)

状态图用于描述系统的行为，将其分解为有限数量的状态及状态之间的转换。

```` markdown title="状态图"
``` mermaid
stateDiagram-v2
  state fork_state <<fork>>
    [*] --> fork_state
    fork_state --> State2
    fork_state --> State3

    state join_state <<join>>
    State2 --> join_state
    State3 --> join_state
    join_state --> State4
    State4 --> [*]
```
````

``` mermaid
stateDiagram-v2
  state fork_state <<fork>>
    [*] --> fork_state
    fork_state --> State2
    fork_state --> State3

    state join_state <<join>>
    State2 --> join_state
    State3 --> join_state
    join_state --> State4
    State4 --> [*]
```

### 类图(Class Diagrams)

类图是面向对象编程的核心，用于通过建模类及它们之间的关系来描述系统结构。

```` markdown title="类图"
``` mermaid
classDiagram
  Person <|-- Student
  Person <|-- Professor
  Person : +String name
  Person : +String phoneNumber
  Person : +String emailAddress
  Person: +purchaseParkingPass()
  Address "1" <-- "0..1" Person:lives at
  class Student{
    +int studentNumber
    +int averageMark
    +isEligibleToEnrol()
    +getSeminarsTaken()
  }
  class Professor{
    +int salary
  }
  class Address{
    +String street
    +String city
    +String state
    +int postalCode
    +String country
    -validate()
    +outputAsLabel()  
  }
```
````

``` mermaid
classDiagram
  Person <|-- Student
  Person <|-- Professor
  Person : +String name
  Person : +String phoneNumber
  Person : +String emailAddress
  Person: +purchaseParkingPass()
  Address "1" <-- "0..1" Person:lives at
  class Student{
    +int studentNumber
    +int averageMark
    +isEligibleToEnrol()
    +getSeminarsTaken()
  }
  class Professor{
    +int salary
  }
  class Address{
    +String street
    +String city
    +String state
    +int postalCode
    +String country
    -validate()
    +outputAsLabel()  
  }
```

### 实体关系图(E-R图, Entity-Relationship Diagrams)

实体关系图由实体类型组成，并描述实体之间的关系，常用于特定领域的知识建模。

```` markdown title="E-R图"
``` mermaid
erDiagram
  CUSTOMER ||--o{ ORDER : places
  ORDER ||--|{ LINE-ITEM : contains
  LINE-ITEM {
    string name
    int pricePerUnit
  }
  CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
```
````

``` mermaid
erDiagram
  CUSTOMER ||--o{ ORDER : places
  ORDER ||--|{ LINE-ITEM : contains
  LINE-ITEM {
    string name
    int pricePerUnit
  }
  CUSTOMER }|..|{ DELIVERY-ADDRESS : uses
```

### 其他类型的图表

除了上述类型，Mermaid.js 还支持饼图、甘特图、用户旅程、Git 图及需求图。然而，Material for MkDocs 对这些图表的支持有限，尤其是在移动端的表现不佳，因此不建议使用这些图表。
另外，虽然 Mermaid.js 的所有功能应开箱即用，但 Material for MkDocs 当前仅为流程图、序列图、类图、状态图和实体关系图调整了字体和颜色。
