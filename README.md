# What is Anchor Modeling?

Anchor modeling is a database modeling approach that emphasizes agility and adaptability. It's particularly useful for data warehouses that need to evolve over time without breaking existing structures.
Core Components

Anchor modeling uses four main building blocks:

1. Anchors

    Represent entities (like Customer, Product, Order)
    Contain only a unique identifier
    Act as the stable "anchor" for information

2. Attributes

    Store descriptive properties about anchors
    Each attribute is stored in its own table
    Include temporal information (when the value was valid)
    Example: CustomerName, CustomerAddress

3. Ties

    Represent relationships between anchors
    Similar to foreign keys, but more flexible
    Can also be temporal
    Example: Customer placed Order

4. Knots

    Store shared reference data
    Like lookup tables for common values
    Example: Country codes, Status types

## Key Principles

Temporal by Design: Everything can track history automatically. Each attribute and tie includes timestamps showing when information was valid.

High Normalization: Each fact is stored once in one place, reducing redundancy.

Extensibility: You can add new attributes without changing existing tables or breaking queries.
Example

Instead of a traditional Customer table:

Customer(ID, Name, Email, City)

Anchor modeling creates:

    Anchor_Customer (ID)
    Attribute_Customer_Name (ID, CustomerID, Name, ValidFrom)
    Attribute_Customer_Email (ID, CustomerID, Email, ValidFrom)
    Attribute_Customer_City (ID, CustomerID, City, ValidFrom)

### Benefits

    Easy to extend without schema changes
    Built-in history tracking
    Handles changes gracefully
    Good for evolving requirements

### Drawbacks

    More complex queries (lots of joins)
    Steeper learning curve
    Can impact query performance
    More tables to manage
