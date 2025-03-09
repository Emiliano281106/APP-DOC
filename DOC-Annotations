# JPA Annotations 

Imagine you have a **toy store**, and people want to ask about toys or buy them. These **JPA annotations** help your store know what to do on your website.  

---

## 1. `@PathVariable` – Finding the Right Toy  
🔹 A customer says: *"I want to see the blue teddy bear!"*  
🔹 You check your shelves and find that exact blue teddy bear.  

✅ **In Java:**  
If someone goes to **/toy/5**, `@PathVariable` helps find toy **number 5**.

```java
@GetMapping("/toy/{id}")
public Toy getToyById(@PathVariable int id) {
    return toyService.findToyById(id);
}
```
📌 Explanation:

The {id} in the URL is a placeholder.
@PathVariable int id takes the value from the URL and passes it to the method.
The method then finds and returns the toy with that ID.


## 2. `@RequestBody` – Taking an Order  
🔹 A customer writes down what they want and gives it to you.  

✅ **In Java:**  
A customer sends:  
📜 *"I want a red car with 4 wheels!"*  
`@RequestBody` reads the note so your store can **add the red car**.

```java
@PostMapping("/toy")
public Toy addToy(@RequestBody Toy newToy) {
    return toyService.saveToy(newToy);
}
```
📌 Explanation:

@RequestBody takes the customer’s request and converts it into a Toy object.
The method saves the new toy in the toy store.
This is used when someone sends data (like a new toy) to be stored.

## 3. `@GetMapping` – Looking at Toys  

Imagine you have a **toy store**, and a customer comes in and says:  
🧸 *"Can I see all the teddy bears?"*  

You show them the shelves **without changing anything**—they can only look.  

---

## 🛒 Real-Life Example  
🔹 A customer asks: *"Can I see all the toys?"*  
🔹 You **show** them but **don’t add or change anything**.  

---

## ✅ `@GetMapping` in Java  

When a customer **wants to see all toys**, `@GetMapping` **retrieves and returns them**.

```java
@GetMapping("/toys")
public List<Toy> getAllToys() {
    return toyService.getAllToys();
}
```

📌 Explanation
✔ @GetMapping("/toys") means "When someone visits /toys, show all toys."
✔This method does not add, change, or delete toys—it only retrieves them.
✔toyService.getAllToys() returns a list of all available toys in the store.

## 4. `@PostMapping` – Adding a New Toy  

Imagine you have a **toy store**, and a customer brings a **new toy** to add to your shelves.  
You take the toy and **place it on the shelf**, so others can buy it later.  

---

## 🛒 Real-Life Example  
🔹 A customer says: *"Here’s a new toy for your store!"*  
🔹 You **take the toy** and **add it to the store**.  

---

## ✅ `@PostMapping` in Java  

When a customer **sends toy details**, `@PostMapping` **adds the new toy**.

```java
@PostMapping("/toys")
public Toy createToy(@RequestBody Toy toy) {
    return toyService.addToy(toy);
}
```

📌 Explanation
✔ @PostMapping("/toys") means "When someone sends toy details, add it to the store."
✔ @RequestBody reads the details of the new toy.
✔ toyService.addToy(toy) saves the toy in the store.
✔ This method creates and returns the new toy.

## 5. `@PutMapping` – Updating an Existing Toy  

Imagine you have a **toy store**, and a customer asks to **update** one of the toys you already have on the shelves.  
You take the toy, **make the changes**, and put it back on the shelf for others to see and buy.  

---

## 🛒 Real-Life Example  
🔹 A customer says: *"Can you paint this car blue instead of red?"*  
🔹 You take the red car, **paint it blue**, and put it back.  

---

## ✅ `@PutMapping` in Java  

When a customer **wants to change a toy**, `@PutMapping` **updates** it with new details.

```java
@PutMapping("/toy/{id}")
public Toy updateToy(@PathVariable int id, @RequestBody Toy updatedToy) {
    return toyService.updateToy(id, updatedToy);
}






