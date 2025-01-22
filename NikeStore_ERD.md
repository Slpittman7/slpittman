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
# Nike Shoe Store ERD

## Overview
This Entity-Relationship Diagram (ERD) shows how the Nike shoe store database manages its operations. The database includes four main entities: **Products**, **Customers**, **Sales**, and **Inventory**. The relationships between these entities are designed to track customer purchases, manage stock levels, and link products to sales.
## Entities and Relationships

1. **Products**:
   - Attributes: `product_id` (PK), `name`, `category`, `price`, and `stock`.
   - Represents the Nike shoes sold in the store.

2. **Customers**:
   - Attributes: `customer_id` (PK), `name`, `email`, and `phone_number`.
   - Contains details of customers who make purchases.

3. **Sales**:
   - Attributes: `sale_id` (PK), `customer_id` (FK), `product_id` (FK), `sale_date`, `quantity`, and `total_price`.
   - Tracks transactions between customers and products.

4. **Inventory**:
   - Attributes: `inventory_id` (PK), `product_id` (FK), and `stock_level`.
   - Manages stock levels for each product.

### Key Relationships
- **Products** and **Inventory**:
  - Each product is linked to its inventory, showing the stock level of that specific shoe model.

- **Customers** and **Sales**:
  - A customer can make multiple purchases, but each sale belongs to only one customer.

- **Sales** and **Products**:
  - Each sale can include multiple products, representing a many-to-many relationship.

## Conclusion
The ERD demonstrates how the database is structured to efficiently manage products, customers, sales, and inventory in the Nike shoe store.
