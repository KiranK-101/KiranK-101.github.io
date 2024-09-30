```mermaid
erDiagram
    PRODUCT {
        int ProductID PK
        string ProductName
        string Category
        float Price
        string Size
        string Color
    }

    CUSTOMER {
        int CustomerID PK
        string Name
        string Email
        string Phone
        string Address
    }

    SALE {
        int SaleID PK
        int CustomerID FK
        int ProductID FK
        int Quantity
        date SaleDate
    }

    INVENTORY {
        int InventoryID PK
        int ProductID FK
        int StockQuantity
    }

    PRODUCT ||--o{ SALE : "sold in"
    CUSTOMER ||--o{ SALE : "makes"
    PRODUCT ||--|| INVENTORY : "tracked in"

```

**Product**: Represents the Nike shoes available in the store, with details such as category, price, and size. This helps keep track of what is available for sale.<br />
**Customer**: Contains customer information to facilitate tracking of sales and customer preferences.<br />
**Sale**: Records each sales transaction, linking the product purchased with the customer.<br />
**Inventory**: Monitors stock levels for each product to ensure availability for customers and manage restocking.
