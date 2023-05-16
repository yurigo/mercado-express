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
### editar productos
### desactivar productos
### buscar productos (por nombre y descripción)
### visualizar productos
### crear categorias
### editar categorias
### eliminar categorias
### visualizar categorias
