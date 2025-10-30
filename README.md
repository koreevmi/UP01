@startuml

' Направление диаграммы: актёры слева, варианты использования справа
left to right direction

' Настройка для прямых линий
skinparam linetype ortho

' Определение актёров
actor Администратор as Admin
actor Инженер as Engineer
actor Гость as Guest

' Определение вариантов использования
usecase Авторизация as Auth
usecase "Управление пользователями" as UserManagement
usecase "Управление материалами" as MaterialManagement
usecase "Просмотр материалов" as ViewMaterials
usecase "Контроль остатков на складах" as StockControl
usecase "Фиксация поставок" as SupplyFixation
usecase "Формирование отчётности" as ReportGeneration
usecase "Просмотр проектов" as ViewProjects
usecase "Управление проектами" as ProjectManagement

' Связи для Администратора
Admin -- Auth
Admin -- UserManagement
Admin -- MaterialManagement
Admin -- ViewMaterials
Admin -- StockControl
Admin -- SupplyFixation
Admin -- ReportGeneration
Admin -- ProjectManagement

' Связи для Инженера
Engineer -- Auth
Engineer -- MaterialManagement
Engineer -- ViewMaterials
Engineer -- StockControl
Engineer -- SupplyFixation
Engineer -- ReportGeneration
Engineer -- ProjectManagement

' Связи для Гостя
Guest -- Auth
Guest -- ViewMaterials
Guest -- ViewProjects

@enduml
