# Product Catalog Service UML

## 1. Classes and Relationships

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

## 2. UML Class Diagram

```mermaid
classDiagram

    class ProductCatalogService {

        +createProduct(productData): Product

        +getProductBySku(sku): Product

        +searchProducts(query): list~Product~

        +listAllProducts(): list~Product~

        +addAttributeToProduct(sku, attribute)

        +getProductAttributes(sku): list~ProductAttribute~

    }

    class Product {

        -sku: SKU

        -name: string

        -description: string

        +updateDetails(newDetails)

        +addImage(image)

        +getImages(): list~Image~

    }

    class SKU {

        -skuValue: string

        +validate()

    }

    class ProductAttribute {

        -name: string

        -value: string

    }

    class Dimension {

        -length: float

        -width: float

        -height: float

        -unit: string

    }

    class Weight {

        -value: float

        -unit: string

    }

    class HandlingRequirement {

        -description: string

    }

    class StorageConstraint {

        -description: string

    }

    class CustomsInfo {

        -countryOfOrigin: string

        -tariffCode: string

    }

    class Image {

        -imageUrl: string

        -altText: string

    }

    ProductCatalogService "1" -- "*" Product

    Product "1" -- "1" SKU

    Product "1" -- "*" ProductAttribute

    ProductAttribute <|-- Dimension

    ProductAttribute <|-- Weight

    ProductAttribute <|-- HandlingRequirement

    ProductAttribute <|-- StorageConstraint

    ProductAttribute <|-- CustomsInfo

    Product "1" -- "*" Image
