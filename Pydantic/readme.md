# Pydantic

A hands-on Python project focused on **data modeling and validation using Pydantic**.

This folder contains two Jupyter Notebooks covering practical use cases of Pydantic, from creating structured models to applying validation rules and handling invalid data.

## 📂 Contents

| Notebook | Topics |
|---|---|
| `Order_model.ipynb` | Pydantic models, nested models, computed properties, and serialization |
| `User_model.ipynb` | Field constraints, email validation, regex validation, and error handling |

## 🧠 Concepts Covered

- Creating models with `BaseModel`
- Type validation using Python type hints
- Field constraints with `Field()`
- Email validation using `EmailStr`
- Nested Pydantic models
- Computed properties
- Dictionary serialization with `model_dump()`
- JSON serialization with `model_dump_json()`
- Handling invalid data with `ValidationError`
- Regex-based validation

## 💡 Practical Examples

### Order Management

The first notebook builds a small order system using:

```text
Customer → Product → Order

```
The `Order` model also calculates the total order amount dynamically using product price and quantity.

### User Validation

The second notebook creates a `User` model with validation rules for:

- Username length
- Email format
- Age range
- Indian phone number pattern
- Password length

## 🛠️ Technologies

- Python
- Pydantic
- Jupyter Notebook

## 🎯 Goal

The goal of this project is to understand how **Pydantic can be used to create structured, validated, and reliable data models**, which are important for building APIs, backend applications, and AI applications.
