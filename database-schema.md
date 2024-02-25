```mermaid
erDiagram
    entity Person {
        person_id INT PRIMARY KEY
        name VARCHAR(255) NOT NULL
        title VARCHAR(255)
        position_start_date DATE
        position_end_date DATE
    }
    entity Organization {
        organization_id INT PRIMARY KEY
        name VARCHAR(255) NOT NULL
        type VARCHAR(255)
    }
    entity Position {
        position_id INT PRIMARY KEY
        title VARCHAR(255) NOT NULL
    }
    entity Interaction {
        interaction_id INT PRIMARY KEY
        occasion VARCHAR(255)
        date DATE
        location VARCHAR(255)
        person_id INT FOREIGN KEY REFERENCES Person(person_id)
        position_id INT FOREIGN KEY REFERENCES Position(position_id)
    }
    Person RELATES TO Organization(1..N) TO MANY Organization
    Person RELATES TO Position(1..N) TO MANY Position
    Person RELATES TO Interaction(1..N) TO MANY Interaction
    Position RELATES TO Interaction(1..N) TO MANY Interaction
```
