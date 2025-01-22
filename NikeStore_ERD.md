```mermaid
erDiagram
    PRODUCT {
        int productID PK
        string name
        string category
        float price
    }
    
    CUSTOMER {
        int customerID PK
        string firstName
        string lastName
        string email
    }
    
    SALE {
        int saleID PK
        int productID FK
        int customerID FK
        date saleDate
        int quantity
    }
    
    INVENTORY {
        int inventoryID PK
        int productID FK
        int stockLevel
    }
    
    PRODUCT ||--o{ INVENTORY : "is stocked in"
    PRODUCT ||--o{ SALE : "is sold in"
    CUSTOMER ||--o{ SALE : "makes"