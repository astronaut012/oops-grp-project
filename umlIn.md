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
