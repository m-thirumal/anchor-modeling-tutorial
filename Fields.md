# Fields

* Identity
* Data Range

## Identity

An `identity` is what uniquely identifies an anchor instance — it’s the immutable key for that entity.

In relational terms: it’s your `primary key`, usually a `surrogate key (BIGINT, UUID, etc.).`

In Anchor Modeling, every Anchor must have exactly one identity.

That identity never changes during the anchor’s lifetime.

## Data Range

A datarange defines what type of data a value (in an attribute, tie, or knot) can hold (Varchar(75), text, etc.).

It’s the domain or data type associated with a concept.

Every attribute and knot in Anchor Modeling has a datarange.