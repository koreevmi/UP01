@startuml

actor Администратор
actor Инженер
actor Гость

usecase Авторизация
usecase "Управление пользователями" as UserManagement
usecase "Управление материалами" as MaterialManagement
usecase "Контроль остатков на складах" as StockControl
usecase "Фиксация поставок" as SupplyFixation
usecase "Формирование отчётности" as ReportGeneration
usecase "Просмотр материалов" as ViewMaterials
usecase "Просмотр проектов" as ViewProjects
usecase "Управление проектами" as ProjectManagement

Администратор --> Авторизация
Администратор --> UserManagement
Администратор --> MaterialManagement
Администратор --> StockControl
Администратор --> SupplyFixation
Администратор --> ReportGeneration
Администратор --> ProjectManagement

Инженер --> Авторизация
Инженер --> MaterialManagement
Инженер --> StockControl
Инженер --> SupplyFixation
Инженер --> ReportGeneration
Инженер --> ProjectManagement

Гость --> Авторизация : "Вход как гость"
Гость --> ViewMaterials
Гость --> ViewProjects

@enduml
