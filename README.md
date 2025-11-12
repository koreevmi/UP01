erDiagram
    Users ||--o{ Projects : "управляет"
    Users ||--o{ Materials : "управляет"
    Users ||--o{ Reports : "формирует"
    Suppliers ||--o{ Materials : "поставляет"
    Projects ||--o{ ProjectMaterials : "включает"
    Materials ||--o{ ProjectMaterials : "используется"
    Materials ||--o{ StockMovements : "имеет"
    Materials }|--|| Suppliers : "поставляется"

    Users {
        int UserId PK
        string Login
        string Password
        string FullName
        string Email
        string Role
    }

    Projects {
        int ProjectId PK
        string Name
        string Description
        datetime StartDate
        datetime EndDate
        decimal Budget
        string Status
    }

    Materials {
        int MaterialId PK
        string Name
        string Unit
        int StockQuantity
        decimal CostPerUnit
        int SupplierId FK
    }

    Suppliers {
        int SupplierId PK
        string Name
        string ContactPerson
        string Phone
        string Email
        string Address
    }

    ProjectMaterials {
        int ProjectMaterialId PK
        int ProjectId FK
        int MaterialId FK
        int PlannedQuantity
        int UsedQuantity
    }

    StockMovements {
        int MovementId PK
        int MaterialId FK
        int Quantity
        string MovementType
        datetime MovementDate
    }

    Reports {
        int ReportId PK
        string Name
        string Type
        datetime CreationDate
        string FilePath
    }
    
---

### Требования для развёртывания системы:

#### Серверная часть:

Для функционирования системы на стороне сервера необходимы следующие программные и технические средства:

- **Операционная система:** Windows Server 2019 или выше.
- **Сервер базы данных:** Microsoft SQL Server 2019.
- **Аппаратные требования:**
  - Процессор: 2 ядра по 2 ГГц или выше.
  - Оперативная память: 4 ГБ или выше.
  - Жёсткий диск: 50 ГБ свободного пространства.
- **Программное обеспечение для администрирования БД:** Microsoft SQL Server Management Studio (SSMS).

---

#### Клиентская часть:

Для функционирования системы на стороне клиента необходимы следующие программные и технические средства:

- **Операционная система:** Windows 10 или выше.
- **Аппаратные требования:**
  - Процессор: частота 1 ГГц или быстрее.
  - Оперативная память: 2 ГБ или выше.
  - Свободное место на диске: 100 МБ.
- **Постоянное интернет-подключение** для взаимодействия с серверной базой данных.

---

Этот текст полностью соответствует вашему стеку технологий (Windows, C#, WPF, Visual Studio 2022, Microsoft SQL Server 2019, SSMS) и требованиям для развёртывания вашего проекта.
