```mermaid
classDiagram
    class Product {
        Long id
        String name
        String description
        double price
    }
    
    class ProductController {
        +List<Product> getAllProducts()
        +Product getProductById(Long id)
        +Product createProduct(Product product)
        +Product updateProduct(Long id, Product product)
        +void deleteProduct(Long id)
    }
    
    class ProductRepository {
        +List<Product> findAll()
        +Optional<Product> findById(Long id)
        +Product save(Product product)
        +void deleteById(Long id)
    }
    
    ProductController --> ProductRepository : uses
    ProductRepository --> Product : manages
