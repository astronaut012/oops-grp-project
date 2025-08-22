# Product Catalog Service Design (Revised)

## 1. Classes and Member Methods

### Class: `ProductCatalogService`

The main service class for managing the product catalog.

| Member Method | Purpose |
| :--- | :--- |
| `createProduct(productData)` | Creates a new product in the catalog. |
| `getProductBySku(sku)` | Retrieves a product by its SKU. |
| `searchProducts(query)` | Searches for products based on a query. |
| `listAllProducts()` | Lists all products in the catalog. |
| `addAttributeToProduct(sku, attribute)` | Adds an attribute to a product. |
| `getProductAttributes(sku)` | Retrieves all attributes for a product. |

### Class: `Product`

Represents a product in the catalog.

| Member Method | Purpose |
| :--- | :--- |
| `__init__(sku, name, description)` | Initializes a new Product object. |
| `updateDetails(newDetails)` | Updates the product's details. |
| `addImage(image)` | Adds an image to the product. |
| `getImages()` | Retrieves all images for the product. |

### Class: `SKU`

Represents a Stock Keeping Unit.

| Member Method | Purpose |
| :--- | :--- |
| `__init__(skuValue)` | Initializes a new SKU object. |
| `validate()` | Validates the format of the SKU. |

### Class: `ProductAttribute` (Base Class)

A generic base class for product attributes.

| Member Method | Purpose |
| :--- | :--- |
| `__init__(name, value)` | Initializes a new ProductAttribute object. |

### Class: `Dimension` (Inherits from `ProductAttribute`)

A specific type of attribute.

| Member Method | Purpose |
| :--- | :--- |
| `__init__(length, width, height, unit)` | Initializes a new Dimension object. |

### Class: `Weight` (Inherits from `ProductAttribute`)

A specific type of attribute.

| Member Method | Purpose |
| :--- | :--- |
| `__init__(value, unit)` | Initializes a new Weight object. |

### Class: `HandlingRequirement` (Inherits from `ProductAttribute`)

A specific type of attribute.

| Member Method | Purpose |
| :--- | :--- |
| `__init__(description)` | Initializes a new HandlingRequirement object. |

### Class: `StorageConstraint` (Inherits from `ProductAttribute`)

A specific type of attribute.

| Member Method | Purpose |
| :--- | :--- |
| `__init__(description)` | Initializes a new StorageConstraint object. |

### Class: `CustomsInfo` (Inherits from `ProductAttribute`)

A specific type of attribute.

| Member Method | Purpose |
| :--- | :--- |
| `__init__(countryOfOrigin, tariffCode)` | Initializes a new CustomsInfo object. |

### Class: `Image`

Represents a product image.

| Member Method | Purpose |
| :--- | :--- |
| `__init__(imageUrl, altText)` | Initializes a new Image object. |


