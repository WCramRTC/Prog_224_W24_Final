**Assignment Title: Starbucks-like App for a cafe called "Why is it still dark outside, Joe? **

**Objective:**
Develop a simple Starbucks-like application enabling users to manage product inventory, process customer orders, and generate receipts.

**Goal**
- Build a simple inventory management system.
- Allow users to add products and services to the inventory.
- Manage inventory data, including name, price, quantity, and additional properties for products and services.
- Implement data persistence by saving and loading inventory data to/from a JSON file.
- Provide a console-based user interface with menu options for adding items, saving inventory data, and performing calculations.
- Calculate and display the total quantity of products in the inventory.
- Calculate and display the total cost of inventory.
- Validate user input for price and quantity to ensure they are valid numerical values.
- Organize code into separate files for each class (`Item`, `Product`, `Service`, `Inventory`) with proper namespace and file organization.
- Use `System.Text.Json` for JSON serialization and deserialization.
- Ensure proper error handling throughout the program.
- Document the code with clear and concise comments explaining the functionality of each class and method.

### Your app ( Your app, must have the following  )

- You are allowed to alter what the app is about. It does not need to be a cafe app, or have the same products. The requirements are
	- Has inheritance with at least 3 classes. With at least one abstract, and two derived classes. 
	- Has to have some form of overriding ( this can be the ToString() )
	- Must have IEnumerable implemented someplace
	- Must save and read from a JSON file
	- When the app opens the data is loaded from the JSON file
	- Must run properly

---

## **Requirements:**

### Project Setup

- Create a new project called "Prog_224_W24_YourName"
- Add your name and project information at of project in comments

### Create the following classes

1. **Create the following classes in Separate Files:**
   - Each class should be contained in a separate file (`Inventory.cs`, `Product.cs`, `Beverage.cs`, `Food.cs`, `Merchandise.cs`, `Order.cs`, `Receipt.cs`).
   - Utilize appropriate namespace and file organization.

2. **Classes:**
   - **`Inventory` Class: (inherits from IEnumerable) **
     - **Fields (Properties):**
       - `Products` (List\<Product>): Collection of products in the inventory.
     - **Methods:**
       - `public void AddProduct(Product product)`: Adds a product to the inventory.
       - `public void RemoveProduct(Product product)`: Removes a product from the inventory.
       - `public void SaveToJson(string filePath)`: Saves inventory data to a JSON file.
       - `public void LoadFromJson(string filePath)`: Loads inventory data from a JSON file.

   - **`Product` Class (Abstract):**
     - **Fields (Properties):**
       - `Name` (string): Name of the product.
       - `Price` (double): Price of the product.
     - **Methods:**
       - `public override string ToString()`: Formats the product information.
       - `public abstract string GetProductType()`: Abstract method to get the type of product.

   - **`Beverage` Class (Inherits from `Product`):**
     - **Fields (Properties):**
       - Inherits all fields from the `Product` class.
       - `Size` (string): Size of the beverage (e.g., small, medium, large).
     - **Methods:**
       - `public override string GetProductType()`: Returns "Beverage".

   - **`Food` Class (Inherits from `Product`):**
     - **Fields (Properties):**
       - Inherits all fields from the `Product` class.
       - `ExpirationDate` (DateTime): Expiration date of the food product.
     - **Methods:**
       - `public override string GetProductType()`: Returns "Food".

   - **`Merchandise` Class (Inherits from `Product`):**
     - **Fields (Properties):**
       - Inherits all fields from the `Product` class.
       - `Category` (string): Category of the merchandise (e.g., clothing, accessories).
     - **Methods:**
       - `public override string GetProductType()`: Returns "Merchandise".

   - **`Order` Class:**
     - **Fields (Properties):**
       - `Products` (List\<Product>): List of products in the order.
       - `TotalPrice` (double): Total price of the order.
     - **Methods:**
       - `public void AddProduct(Product product)`: Adds a product to the order.
       - `public double CalculateTotalPrice()`: Calculates the total price of the order.

   - **`Receipt` Class:**
     - **Fields (Properties):**
       - `Order` (Order): Order for which the receipt is generated.
       - `TotalPrice` (double): Total price of the order.
     - **Methods:**
       - `public override string ToString()`: Formats the receipt information.

### Data Persistence

7. **Data Persistence:**
   - Implements data persistence to save and load inventory data and receipt details using JSON serialization and deserialization.
   - Ensures proper error handling and validation for file operations.

### Create a Simple Menu

3. **User Interface:**
   - Implement a simple console-based user interface with the following menu options:
     - Display Products: Shows available products with their names and prices.
     - Add Product: Enables users to add new products to the inventory.
     - Ring Up Customer: Allows users to create orders for customers, add products to their orders.
     - Exit: Terminates the program.

```console
Welcome to the Why is it still dark outside, Joe? App
1. Display Products
2. Add Product
3. Ring Up Customer
4. Exit
```

4. **Display Products:**
   - Shows available products with their names and prices.

```console
Welcome to the Why is it still dark outside, Joe? App
1. Display Products
2. Add Product
3. Ring Up Customer
4. Exit
Enter your choice: 1

Available Products:
1. Coffee: $2.5
2. Croissant: $3
3. Mug: $10
```

5. **Add Product:**
   - Enables users to input details (name, price) of a new product and add it to the available products.

```console
// 2. Adding the product -----------------------------------------
Welcome to the Why is it still dark outside, Joe? App
1. Display Products
2. Add Product
3. Ring Up Customer
4. Exit
Enter your choice: 2

Enter product name: Latte
Enter product price: 4.5
Select product type:
1. Beverage
2. Food
3. Merchandise
Enter your choice: 1
Enter beverage size: Medium
Product added successfully!
```

6. **Ring Up Customer:**
   - Allows users to create an order for a customer, adding products to their order.
   - Calculates the total price of the order.
   - Generates a receipt for the order.

```
3. Creating an order ---------------------------------------------
Welcome to the Why is it still dark outside, Joe? App
1. Display Products
2. Add Product
3. Ring Up Customer
4. Exit
Enter your choice: 3

Select a product to add to the order:
1. Coffee: $2.5
2. Croissant: $3
3. Mug: $10
4. Latte: $4.5
Enter product number: 1
Product added to the order.
Do you want to add more products to the order? (yes/no): yes
Select a product to add to the order:
1. Coffee: $2.5
2. Croissant: $3
3. Mug: $10
4. Latte: $4.5
Enter product number: 2
Product added to the order.
Do you want to add more products to the order? (yes/no): no
Total price of the order: $5.5
Receipt:
Order Total: $5.5
```

### Exit the app

```
4. Exiting the app --------------------------------------------------------

Welcome to the Why is it still dark outside, Joe? App
1. Display Products
2. Add Product
3. Ring Up Customer
4. Exit
Enter your choice: 4
```

### Final Requirements
- Must run without any compilation errors.
- Must have comments
- Push to github and submit your repository link
---

### Rubric

| Name                   | Description                                                                                                                       | Points |
| ---------------------- | --------------------------------------------------------------------------------------------------------------------------------- | ------ |
| Project Setup          | Evaluation of project setup including proper naming, organization, and comments.                                                  | 20     |
| Menu Functionality     | Assessment of the structure and functionality of the menu options.                                                                | 40     |
| Saving to JSON         | Assessment of the implementation of JSON serialization and deserialization for persistence of inventory data and receipt details. | 60     |
| Classes Implementation | Examination of the implementation of classes, inheritance, overriding, and IEnumerable.                                           | 50     |
| Comments               | Presence of sufficient and relevant comments throughout the code.                                                                 | 30     |

Total Points: 200
