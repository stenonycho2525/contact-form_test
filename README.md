## ER図

```mermaid
erDiagram
    users {
        bigint id PK
        string name
        string email
        string tel
        text content
        timestamp created_at
        timestamp updated_at
    }
```