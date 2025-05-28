

# Product Categorization Methodology

## 1. Building the Category Structure

### 1.1 Main Categories

I started by creating five broad categories. Each product was manually placed into one of these main groups:

* **Home & Living**
* **Personal Items**
* **Entertainment & Hobbies**
* **Seasonal & Gifts**
* **Office & Craft**

These categories helped simplify the initial classification process and reduce confusion.

### 1.2 Subcategories

Next, i broke each main category down into more specific subcategories. This was done by manually analyzing products:

#### **Home & Living**

* Home Decor
* Lighting
* Kitchen & Dining
* Textiles & Cozy Items
* Garden & Outdoor
* Bath & Body
* Storage & Organization
* Pets & Animals

#### **Personal Items**

* Fashion & Accessories
* Electronics & Gadgets

#### **Entertainment & Hobbies**

* Kids & Toys
* Books & Magazines
* Games & Puzzles
* Vintage & Collectibles

#### **Seasonal & Gifts**

* Seasonal & Holidays
* Gifts & Special Occasion
* Party Supplies

#### **Office & Craft**

* Stationery & Office
* Crafts & DIY

## 2. Classifying the Products

### 2.1 Using Automation

I used the OpenAI API to automatically assign products to the right subcategory. The model had access to this full list of categories:

```python
possible_categories = [
    "Home Decor",
    "Lighting",
    "Kitchen & Dining",
    "Textiles & Cozy Items",
    "Kids & Toys",
    "Garden & Outdoor",
    "Stationery & Office",
    "Seasonal & Holidays",
    "Gifts & Special Occasion",
    "Bath & Body",
    "Party Supplies",
    "Crafts & DIY",
    "Vintage & Collectibles",
    "Storage & Organization",
    "Electronics & Gadgets",
    "Pets & Animals",
    "Fashion & Accessories",
    "Books & Magazines",
    "Games & Puzzles",
    "Miscellaneous"
]
```

### 2.2 Manual Review

After the automated process, each product’s category was reviewed by hand. This final step helped catch any mistakes and made sure all items were placed logically and consistently.
