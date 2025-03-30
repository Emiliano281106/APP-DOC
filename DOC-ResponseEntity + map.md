# Explanation of `@GetMapping` Example with `Optional`

This code is an example of how you can use `@GetMapping` in a Spring Boot controller to fetch a **Level** object by its `id`. It uses `Optional` to handle the case where the level might not exist and returns an appropriate HTTP response.

---

### **Code Breakdown:**

```java
@GetMapping("/{id}")
public ResponseEntity<Level> getLevelById(@PathVariable String id) {
    Optional<Level> level = levelService.getLevelById(id);

    return level.map(ResponseEntity::ok)
                .orElseGet(() -> ResponseEntity.status(HttpStatus.NOT_FOUND).build());
}
```
# Step-by-Step Explanation:

### `@GetMapping("/{id}")`

This annotation tells Spring that this method should handle **GET** requests to the `/` endpoint, where `{id}` is a path variable representing the level's `id`.  
For example, a GET request like `/level/1` would call this method with the `id` of `1`.

---

### `@PathVariable String id`

This annotation binds the value of the `{id}` path variable in the URL to the `id` parameter of the method.  
In the example, if the URL is `/level/1`, the method will receive `id` as `"1"`.

---

### `Optional<Level> level = levelService.getLevelById(id);`

This line calls the `levelService.getLevelById(id)` method, which returns an **Optional** object that may or may not contain a `Level` object.  
`Optional` is used here to avoid returning a `null` value if no level is found for the provided `id`.

---

### `level.map(ResponseEntity::ok)`

The `map()` function is used on the **Optional** to check if a value is present.  
If the `Optional` contains a `Level`, it is passed to `ResponseEntity.ok(level)`, which returns a **200 OK** response with the `Level` as the body.

---

### `.orElseGet(() -> ResponseEntity.status(HttpStatus.NOT_FOUND).build())`

If the **Optional** is empty (i.e., the `Level` is not found), the `orElseGet()` method is called.  
It creates a **404 Not Found** response using `ResponseEntity.status(HttpStatus.NOT_FOUND).build()`.  
This means no `Level` was found, and the response will indicate that with a **404 status** and an empty body.

---

## How It Works:

1. If the **level exists** (i.e., the `Optional` contains a value), the response will have:  
   - **HTTP Status**: `200 OK`  
   - **Body**: The `Level` object.

2. If the **level does not exist** (i.e., the `Optional` is empty), the response will have:  
   - **HTTP Status**: `404 Not Found`  
   - **Body**: No body.

---

## Summary:

- `@GetMapping("/{id}")`: Handles **GET** requests to fetch a level by `id`.  
- `@PathVariable String id`: Binds the `id` from the URL to the method parameter.  
- `Optional<Level>`: Safely handles cases where a level may or may not exist.  
- `map(ResponseEntity::ok)`: Returns a **200 OK** response if the level is found.  
- `orElseGet(() -> ResponseEntity.status(HttpStatus.NOT_FOUND).build())`: Returns a **404 Not Found** response if the level is not found.
