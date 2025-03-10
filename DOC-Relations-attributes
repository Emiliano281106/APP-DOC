# PROAPP-DOC
# 📦 JPA Relationship Attributes Explained Like You’re 5  

Imagine you have a **toy box**, and inside the toy box, you have different kinds of **toys**. Now, let's compare this to how relationships work in **JPA (Java Persistence API) in Spring Boot**.

---

## 1️⃣ `fetch` (How Quickly You Get Your Toys)  
Think of **fetch** like how you get your toys from the box.

- **EAGER** → As soon as you open the box, **all the toys come out immediately**.  
- **LAZY** → You open the box, but the toys **stay inside**. You only take them out **when you ask for them**.

👉 In JPA, `FetchType.LAZY` means data is loaded **only when needed**, while `FetchType.EAGER` loads everything **immediately**.

---

## 2️⃣ `cascade` (What Happens to Your Toys When You Do Something to the Box?)  
Imagine you have a **big toy box (`Parent`)** and inside it, **smaller toy boxes (`Children`)**.

If you **throw away** the big box, what should happen to the small boxes inside?

- **`CascadeType.ALL`** → If you throw away the big box, **all small boxes inside are also thrown away**.
- **`CascadeType.PERSIST`** → If you buy a new big box, the **small boxes inside also get saved**.
- **`CascadeType.REMOVE`** → If you remove the big box, the **small boxes are also removed**.
- **`CascadeType.MERGE`** → If you fix the big box, **the small boxes inside also get updated**.

👉 This tells JPA **what to do with related entities when something happens to the parent**.

---

## 3️⃣ `orphanRemoval` (What Happens to Lonely Toys?)  
Now, imagine you take one **toy** out of the toy box and just leave it outside.

- If **`orphanRemoval = true`**, that toy gets **thrown away automatically**.  
- If **`orphanRemoval = false`**, the toy just **sits outside but is still there**.

👉 In JPA, `orphanRemoval = true` automatically **deletes child entities if they are removed from the parent**.

---

## 4️⃣ `mappedBy` (Who Owns the Toys?)  
Now, imagine you and your **friend** both have a **toy box**, but you **share some toys**.  
Who decides **where the toys are stored**?

- The `mappedBy` tells JPA **which side is the boss (owns the relationship)**.

### Example:  
```java
class Parent {
    @OneToMany(mappedBy = "parent")  // "parent" is the field in Child
    List<Child> children;
}

class Child {
    @ManyToOne
    Parent parent;
}
```
## 🔹 When to Use `mappedBy`?  
Use **`mappedBy`** on the side that **DOES NOT** own the relationship (usually the `@OneToMany` side).  
The **foreign key** is stored in the **Many-To-One (`@ManyToOne`)** side.

| **Annotation**                     | **Who Owns the Relationship?** |
|------------------------------------|--------------------------------|
| `@OneToMany` **without** `mappedBy` | **Both sides track the relationship (redundant)** |
| `@OneToMany(mappedBy = "fieldName")` | **Only the `@ManyToOne` side tracks it (correct way)** |


## 5️⃣ `optional` (Do You Always Need a Toy Box?)  
Imagine you want to **play with toys**.

- If **`optional = true`**, you **can** play **without a toy box**.  
- If **`optional = false`**, you **must** have a toy box to play.

### Example:  
```java
@ManyToOne(optional = false)  
Parent parent;  // A child MUST have a parent
```
## 🔥 Summary  

| **Attribute**      | **Meaning (Toy Box Example)** |
|-------------------|-----------------------------|
| `fetch`           | Do toys come out **immediately** or **only when needed**? |
| `cascade`         | What happens to **small boxes** if you throw away the **big one**? |
| `orphanRemoval`   | Should **lonely toys** be thrown away? |
| `mappedBy`        | **Who owns the toys?** |
| `optional`        | **Do you always need a toy box?** |
