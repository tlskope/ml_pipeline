# End to end ML Pipeline for Price Prediction 
## Using ZenML and MLflow

## Key Ideas

1. Understand the Data
2. Understand which models perform best for the data type
3. Iterate to understand what is working.

## Method

1. Thorough Data Research
2. Structured Data Processing
3. Beyond Core ML
4. MLOps and Production Readiness

### Beginning Steps:

1. Factory design pattern method

An example of implementation of the factory design method:

```bash
from abc import ABC, abstractmethod


# Step 1: Define the Product interface
class Coffee(ABC):
    @abstractmethod
    def prepare(self):
        pass


# Step 2: Implement Concrete Products
class Espresso(Coffee):
    def prepare(self):
        return "Preparing a rich and strong Espresso."


class Latte(Coffee):
    def prepare(self):
        return "Preparing a smooth and creamy Latte."


class Cappuccino(Coffee):
    def prepare(self):
        return "Preparing a frothy Cappuccino."


# Step 3: Implement the Factory (CoffeeMachine)
class CoffeeMachine:
    def make_coffee(self, coffee_type):
        if coffee_type == "Espresso":
            return Espresso().prepare()
        elif coffee_type == "Latte":
            return Latte().prepare()
        elif coffee_type == "Cappuccino":
            return Cappuccino().prepare()
        else:
            return "Unknown coffee type!"


# Step 4: Use the Factory to Create Products
if __name__ == "__main__":
    machine = CoffeeMachine()

    coffee = machine.make_coffee("Espresso")
    print(coffee)  # Output: Preparing a rich and strong Espresso.

    coffee = machine.make_coffee("Latte")
    print(coffee)  # Output: Preparing a smooth and creamy Latte.

    coffee = machine.make_coffee("Cappuccino")
    print(coffee)  # Output: Preparing a frothy Cappuccino.
```