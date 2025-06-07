# Skin Care Product Management System

```python
"""
A Python system for managing skin care product inventory with sales and restocking capabilities.
Main components:
- main.py: User interface and program flow
- read.py: Product data reading functionality
- write.py: Invoice generation
- operation.py: Business logic
- products.txt: Product database
"""

# Key Features:
# 1. Product Management
#    - View all products with details (name, brand, country, quantity, price)
#    - Automatic price calculation (200% markup + 13% VAT)
#    - "Buy 3 Get 1 Free" promotion
#
# 2. Sales Processing
#    - Customer purchase tracking
#    - Automatic invoice generation (itemized list with VAT)
#
# 3. Inventory Management
#    - Real-time stock updates
#    - Persistent storage in products.txt

# Requirements:
# - Python 3.x
# - No additional dependencies

# Run the system:
python main.py

skin-care-system/
├── main.py            # Main program interface
├── read.py            # Product data reader
├── write.py           # Invoice generator
├── operation.py       # Business logic
├── products.txt       # Product database

# Sample workflow:

# 1. Display products
def display_products():
    print("Available Products:")
    print("-" * 116)
    print(f"| {'S.N.':<5} | {'Product Name':30} | {'Brand':20} | {'Country':20} | {'Quantity':10} | {'Price (NPR)':12} |")

# 2. Sell products
def sell_products():
    customer_name = input("Enter customer name: ")
    # Product selection logic...
    # Invoice generation...
    print("Invoice generated!")

# 3. Restock products  
def restock_products():
    vendor_name = input("Enter vendor name: ")
    # Restock logic...
    print("Inventory updated!")

# products.txt format:
# ProductName,Brand,Quantity,CostPrice,Country

# Example:
"Vitamin C Serum,Garnier,200,1000.0,France"
"Skin Cleanser,Cetaphil,100,280.0,Switzerland"

# operation.py contains core calculations:

def calculate_selling_price(cost_price):
    """200% markup + 13% VAT"""
    return cost_price * 2 * 1.13

def update_product(products, product_name, quantity_sold):
    """Apply 'Buy 3 Get 1 Free' promotion"""
    free_items = quantity_sold // 3
    total_deduction = quantity_sold + free_items
    # Inventory update logic...

==========================================================================
          INVOICE
==========================================================================
Date          : 2023-11-15 14:30:45
Customer Name : John Doe
--------------------------------------------------------------------------
S.N. Product Name          Quantity   Unit Price (NPR)   Total (NPR)
1     Sunscreen            3          1580.00            4740.00
--------------------------------------------------------------------------
                        Subtotal: NPR 4194.69
                        VAT (13%): NPR 545.31
                        Total Amount: NPR 4740.00
==========================================================================
Thank you for shopping!

MIT License - Free for personal and commercial use
