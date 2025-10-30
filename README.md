@startuml

' Направление диаграммы: актёры слева, варианты использования справа
left to right direction

' Определение актёров
actor Администратор as Admin
actor Инженер as Engineer
actor Гость as Guest

' Определение вариантов использования
usecase "Авторизация" as Auth
usecase "Управление пользователями" as UserManagement
usecase "Управление материалами" as MaterialManagement
usecase "Контроль остатков на складах" as StockControl
usecase "Фиксация поставок" as SupplyFixation
usecase "Формирование отчётности" as ReportGeneration
usecase "Просмотр материалов" as ViewMaterials
usecase "Просмотр проектов" as ViewProjects
usecase "Управление проектами" as ProjectManagement

' Связи для Администратора
Admin --> Auth : "Вход в систему"
Admin --> UserManagement : "Добавление, редактирование\nи удаление пользователей"
Admin --> MaterialManagement : "Добавление, редактирование\nи удаление материалов"
Admin --> StockControl : "Обновление данных\nоб остатках материалов"
Admin --> SupplyFixation : "Фиксация поставок\nи обновление остатков"
Admin --> ReportGeneration : "Генерация отчётов\nпо материалам и проектам"
Admin --> ProjectManagement : "Добавление, редактирование\nи удаление проектов"

' Связи для Инженера
Engineer --> Auth : "Вход в систему"
Engineer --> MaterialManagement : "Добавление, редактирование\nи удаление материалов"
Engineer --> StockControl : "Обновление данных\nоб остатках материалов"
Engineer --> SupplyFixation : "Фиксация поставок\nи обновление остатков"
Engineer --> ReportGeneration : "Генерация отчётов\nпо материалам и проектам"
Engineer --> ProjectManagement : "Просмотр и управление\nматериалами в проектах"

' Связи для Гостя
Guest --> Auth : "Вход как гость"
Guest --> ViewMaterials : "Просмотр каталога\nматериалов"
Guest --> ViewProjects : "Просмотр списка\nпроектов"

@enduml
