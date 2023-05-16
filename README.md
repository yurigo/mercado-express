# mercado-express
Gestion de productos/regalos para social-gift u otro servicio...

## Gestion de productos 

- crear productos
- editar productos
- desactivar productos
- buscar productos (por nombre y descripción)
- visualizar productos

## Gestion de categorias

- crear categorias
- editar categorias
- eliminar categorias
- visualizar categorias

# Casos de uso

TBD

# Base de datos

| PRODUCTS |
| --- | 
| id |
| name |
| description |
| image_url |
| url <?> |
| price |
| stock |
| deleted |

| CATEGORIES |
| --- |
| id |
| name |
| description |
| image_url |
| parent_id |

| PRODUCTS_CATEGORIES |
| --- |
| product_id |
| category_id |

## Enpoints // Representaciones

### crear productos

```
POST /products/
{
    name
    description
    image_url
    url
    price
    stock
    category: [ 1 , 2 , 3 ]
}
```

### editar productos

```
PUT /products/:id
{
    name
    description
    image_url
    url
    price
    stock
    category: [ 1 , 2 , 3 ]
}
```



### desactivar productos
```
DELETE /products/:id
```
Hacemos un borrado lógico: Update de la tabla products y pondrá el delete en true.

### visualizar productos
```
GET /products?page=10&offset=20
GET /products?limit=10&page=10&offset=20&columns=name,description,stock
```

### visualizar UN producto
```
GET /products/:id
```

### buscar productos (por nombre y/o descripción)
```
GET /products/search
{
    criteria
}
```

```
GET /products/search/:criteria
```

```
GET /products?limit=10&page=10&offset=20&columns=name,description,stock
```

```
GET /products?search=loquequierobuscar
```

Ejemplo de búsqueda:
```
-- PRODUCTS --
id: 1
nombre: playstation 5
descripcion: ps5, consola playstation 5. 
```

```
SELECT * FROM products
WHERE 
   name LIKE '%params.search%' OR
   description LIKE '%params.search%'

```



### crear categorias

```
POST /categories
{
    name
    description
    image_url
    // será categoría raiz
}

POST /categories
{
    name
    description
    image_url
    parent_id // <-- será hijo de
}
```


### editar categorias

```
PUT /categories/:id
{
    name
    description
    image_url
    parent_id
}
```

### eliminar categorias
```
DELETE /categories/:id
```


### visualizar categoria

```
GET /categories/:id
```

### visualizar categorias

```
GET /categories
```

