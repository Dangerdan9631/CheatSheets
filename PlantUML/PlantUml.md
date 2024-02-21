# Plant UML
[Full Documentation](https://pdf.plantuml.net/1.2020.22/PlantUML_Language_Reference_Guide_en.pdf)

## Sequence Diagrams
### Basic
**Diagram Basics**
```plantuml
@startuml Diagram Basics
skinparam ResponseMessageBelowArrow true

actor Actor #Red
boundary Boundary #Blue
control Control #Green
entity Entity #Yellow
database Database #White
collections Collections #CornflowerBlue
participant "Participant\n1" as P1 #LightGreen

Actor -> Boundary : To boundary
Actor -> Control : To control
Actor -> Entity : To entity
Actor -> Database : To database
Actor -> Collections : To collections
Actor -> Actor : To self\nwith multiline text
Collections --> Actor : Response
@enduml
```
![Diagram Basics](DiagramBasics.png)

**Basic Arrows**
```plantuml
@startuml Basic Arrows
skinparam ResponseMessageBelowArrow true

Alice -> Bob : "->"
Alice ->x Bob : "->x"
Alice ->> Bob : "->>"
Alice -\ Bob : "-\"
Alice \\- Bob : "\\-"
Alice //- Bob : "//-"

autonumber
Alice ->o Bob : "->o"
Alice o\\- Bob : "o\\-"

autonumber 15
Alice <-> Bob : "<->"
Alice <->o Bob : "<->o"
autonumber stop

Alice o<->o Bob : "o<->o"

autonumber 40 10
Alice -[#Red]> Bob : "-[#Red]>"
Alice -[#0000FF]-> Bob : "-[#0000FF]->"
@enduml
```
![Basic Arrows](BasicArrows.png)

**Basic Formatting**
```plantuml
@startuml Basic Formatting
title Basic Formatting
skinparam maxMessageSize 50

alt
    Alice -> Bob : alt
    note left : Left note here
else
    Alice -> Bob : else
    note right : Right note here
end
...
opt
    Alice -> Bob : opt
    note left of Bob : Left of Bob
end
...5 minutes later...
loop
    note over Alice : Over Alice
    loop nested loop
        Alice -> Bob : loop
    end
    note over Alice, Bob : Over Alice, Bob
end
== A divider ==
group Any arbitrary title
    Alice -> Bob : group
    note right
        Multiline
        note
    end note
end
|||
Alice -> Bob : Whitespace
||40||
Alice -> Bob : Big Whitespace
@enduml
```
![Basic Formatting](BasicFormatting.png)

### Lifelines
**Lifelines**
```plantuml
@startuml Lifelines
participant User
[-> A : Do Work
activate A #Red

A -> B : Create Request
activate A #Blue
activate B

B -> C : Do Work
activate C

C ->] : External Call
C <--] : External Response

C --> B : Work Done
destroy C

B --> A : Request Created
deactivate B
deactivate A #Blue

[<-- A : Done
deactivate A

@enduml
```
![Lifelines](Lifelines.png)

**Autoactivate**
```plantuml
@startuml Autoactivate
autoactivate on
participant User

User -> A : Do Work

A -> B : Create Request

B -> C ** : Do Work
return Request Created

return Done

@enduml
```
![Auto Activate](AutoActivate.png)