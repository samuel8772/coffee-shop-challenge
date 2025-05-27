# ☕ Coffee Shop Project

This is a Python object-oriented programming (OOP) project simulating a coffee shop system. It models `Customer`, `Coffee`, and `Order` objects and explores concepts like data encapsulation, object relationships, type enforcement, and basic aggregation.

---

## 📁 Project Structure

```
coffee-shop-proj/
├── Pipfile                # Python environment configuration
├── debug.py               # Manual testing and debugging
├── customer.py            # Customer class and logic
├── coffee.py              # Coffee class and logic
├── order.py               # Order class and logic
└── tests/                 # Folder containing test scripts
    ├── customer_test.py
    ├── coffee_test.py
    └── order_test.py
```

---

## ⚙️ Setup Instructions

1. **Clone the Repository**
   ```bash
   git clone git@github.com:samuel8772/coffee-shop-proj.git
   cd coffee-shop-proj
   ```

2. **Set Up Python Environment with Pipenv**
   ```bash
   pipenv install
   pipenv shell
   ```

3. **Run Debug File (For Manual Testing)**
   ```bash
   python debug.py
   ```

---

## 📚 Domain Overview

The Coffee Shop domain consists of:

- A `Customer` has many `Orders`
- A `Coffee` has many `Orders`
- An `Order` belongs to one `Customer` and one `Coffee`

This forms a **many-to-many** relationship between `Customer` and `Coffee`, connected through `Order`.

---

## ✅ Project Requirements

### 1. Models & Initializers

#### 🧍 Customer

```python
def __init__(self, name: str)
```

- Must store a name (string, 1–15 characters)
- Has a `name` property:
  - Getter returns the name
  - Setter enforces that name is a string and 1–15 characters

#### ☕ Coffee

```python
def __init__(self, name: str)
```

- Must store a name (string, minimum 3 characters)
- Has a `name` property:
  - Getter returns the name
  - **Immutable** (no setter after initialization)

#### 🧾 Order

```python
def __init__(self, customer: Customer, coffee: Coffee, price: float)
```

- Requires a `Customer`, `Coffee`, and a `price` (float between 1.0 and 10.0)
- Has a `price` property:
  - Getter returns the price
  - **Immutable** once set

---

### 2. Object Relationships

- `Order.customer` → returns the associated `Customer` object  
- `Order.coffee` → returns the associated `Coffee` object  
- `Customer.orders()` → list of `Order` objects for the customer  
- `Customer.coffees()` → unique list of `Coffee` objects the customer has ordered  
- `Coffee.orders()` → list of `Order` objects for the coffee  
- `Coffee.customers()` → unique list of `Customer` objects who ordered the coffee  

---

### 3. Aggregates & Associations

- `Customer.create_order(coffee, price)`  
  Instantiate a new `Order`, linked to the customer and the given coffee.

- `Coffee.num_orders()`  
  Returns the total number of orders for that coffee.

- `Coffee.average_price()`  
  Returns the average price of all orders for that coffee.

---

### 4. 🏆 Bonus (Optional)

#### `Customer.most_aficionado(coffee)`

```python
@classmethod
def most_aficionado(cls, coffee: Coffee)
```

- Returns the `Customer` who has **spent the most** on the given coffee.
- Returns `None` if there are no orders.

---

## 🧪 Testing

Use the provided test scripts to verify behavior:

```bash
python tests/customer_test.py
python tests/coffee_test.py
python tests/order_test.py
```

Or test manually via:

```bash
python debug.py
```

---

## 🗒️ Notes

- Use Python OOP principles (encapsulation, single source of truth).
- Do **not** use external libraries beyond the standard library.
- Ensure validations and type checks are properly implemented.

---

## 👨‍💻 Author

**Samuel Karobia**  
GitHub: [@samuel8772](https://github.com/samuel8772)  
Email: kamauskk005@gmail.com  

---

## 📜 License

This project is for educational purposes under the Flatiron School / Moringa School curriculum. Not licensed for commercial use.
