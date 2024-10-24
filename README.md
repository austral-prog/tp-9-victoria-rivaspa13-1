[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/zYh7d0Iz)
# Trabajo Práctico 9


## Diccionarios 

En este ejercicio, administrarás un sistema de inventario.

El inventario debe estar organizado por el nombre del artículo y debe llevar un seguimiento del número de artículos disponibles.

Tendrás que gestionar la adición de artículos a un inventario. Cada vez que un artículo aparezca en una lista dada, aumenta la cantidad del artículo en `1` en el inventario. Luego, tendrás que gestionar la eliminación de artículos de un inventario.

Para finalizar, tendrás que implementar una función que devuelva todos los pares clave-valor en un inventario como una lista de `tuplas`.

### 1. Crear un inventario basado en una lista

Implementa la función `create_inventory` que crea un "inventario" a partir de una lista de artículos. Debe devolver un `dict` que contenga cada nombre de artículo emparejado con su cantidad respectiva.

```python
>>> create_inventory(["coal", "wood", "wood", "diamond", "diamond", "diamond"])
{"coal":1, "wood":2, "diamond":3}
```

### 2. Añadir artículos a partir de una lista a un diccionario existente

Implementa la función `add_items` que agrega una lista de artículos a un inventario:

```python
>>> add_items({"coal":1}, ["wood", "iron", "coal", "wood"])
{"coal":2, "wood":2, "iron":1}
```

### 3. Decrementar artículos del inventario

Implementa la función `decrement_items` que toma una `lista` de artículos. La función debe restar uno de la cantidad disponible en el inventario por cada vez que un artículo aparezca en la `lista`:

```python
>>> decrement_items({"coal":3, "diamond":1, "iron":5}, ["diamond", "coal", "iron", "iron"])
{"coal":2, "diamond":0, "iron":3}
```
Las cantidades de los artículos en el inventario no deben caer por debajo de 0. Si la cantidad de veces que un artículo aparece en la lista excede la cantidad disponible, la cantidad listada para ese artículo debe permanecer en 0 y las solicitudes adicionales para eliminar cantidades deben ser ignoradas.

```python
>>> decrement_items({"coal":2, "wood":1, "diamond":2}, ["coal", "coal", "wood", "wood", "diamond"])
{"coal":0, "wood":0, "diamond":1}
```

### 4. Eliminar por completo un artículo del inventario

Implementa la función `remove_item` que elimina un artículo y su cantidad completamente de un inventario:

```python
>>> remove_item({"coal":2, "wood":1, "diamond":2}, "coal")
{"wood":1, "diamond":2}
```
Si el artículo no se encuentra en el inventario, la función debe devolver el inventario original sin cambios.
```python
>>> remove_item({"coal":2, "wood":1, "diamond":2}, "gold")
{"coal":2, "wood":1, "diamond":2}
```

### 5. Devolver el contenido del inventario

Implementa la función `list_inventory` que toma un inventario y devuelve una lista de tuplas `(artículo, cantidad)`. La lista solo debe incluir los artículos disponibles (con una cantidad mayor a cero):

```python
>>> list_inventory({"coal":7, "wood":11, "diamond":2, "iron":7, "silver":0})
[('coal', 7), ('diamond', 2), ('iron', 7), ('wood', 11)]
```