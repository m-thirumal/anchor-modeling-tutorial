# What is Anchor Modeling?

Anchor modeling is a database modeling approach that emphasizes agility and adaptability. It's particularly useful for data warehouses that need to evolve over time without breaking existing structures.

Anchor modeling uses four main building blocks / Core Components:

1. [Anchors](Anchor.md)
2. [Attributes](Atribute.md)
3. [Ties](Tie.md)
4. [Knots](Knot.md)

## Key Principles

Temporal by Design: Everything can track history automatically. Each attribute and tie includes timestamps showing when information was valid.

`High Normalization:` Each fact is stored once in one place, reducing redundancy.

`Extensibility:` You can add new attributes without changing existing tables or breaking queries.

`Table Elimination`:  

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
