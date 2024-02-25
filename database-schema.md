```mermaid
erDiagram
    interaction_details {
        interaction_id INT
        title VARCHAR(255)
        location VARCHAR(255)
        date DATE
        notes TEXT
    }
    interaction_participants {
        interaction_id INT
        career_id INT
    }
    careers {
        person_id INT
        career_id INT
        organization_id INT
        name VARCHAR(255)
        title VARCHAR(255)
        position_start_date DATE
        position_end_date DATE
    }
    people {
        person_id INT
        name VARCHAR(255)
        linkedin VARCHAR(255)
    }
    organizations {
        organization_id INT
        organization_name VARCHAR(255)
        organization_type VARCHAR(255)
    }

    interaction_details }|--|{ interaction_participants : interaction_id
    interaction_participants }|--|{ careers : career_id
    careers }|--|| people : person_id
    careers }|--|{ organizations : organization_id
```
