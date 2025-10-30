@startuml

left to right direction
skinparam linetype ortho

' Актёры
actor Администратор as Admin
actor Инженер as Eng
actor Гость as Guest

' Варианты использования
usecase Авторизация as Auth
usecase "Управление пользователями" as UserManagement
usecase "Управление материалами" as MaterialManagement
usecase "Контроль остатков на складах" as StockControl
usecase "Фиксация поставок" as SupplyFixation
usecase "Формирование отчётности" as ReportGeneration
usecase "Просмотр материалов" as ViewMaterials
usecase "Просмотр проектов" as ViewProjects
usecase "Управление проектами" as ProjectManagement

' Связи для Администратора
Admin -- Auth
Admin -- UserManagement
Admin -- MaterialManagement
Admin -- StockControl
Admin -- SupplyFixation
Admin -- ReportGeneration
Admin -- ProjectManagement
Admin -- ViewMaterials

' Связи для Инженера
Eng -- Auth
Eng -- MaterialManagement
Eng -- StockControl
Eng -- SupplyFixation
Eng -- ReportGeneration
Eng -- ProjectManagement
Eng -- ViewMaterials

' Связи для Гостя
Guest -- Auth : "Вход как гость"
Guest -- ViewMaterials
Guest -- ViewProjects

' Группировка вариантов использования
rectangle MaterialManagement {
    MaterialManagement
    StockControl
    SupplyFixation
}

rectangle Reporting {
    ReportGeneration
}

rectangle ProjectManagementGroup {
    ProjectManagement
    ViewProjects
}

@enduml
