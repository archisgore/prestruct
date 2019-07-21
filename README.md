# PreStruct
Second Order *Pre*dicate-Logic Infra*struct*ure: Infrastructure as Code + Declaractive Infrastructure.

# The problem

After a [blog post](https://medium.com/@archisgore/can-we-just-cut-to-infrastructure-as-declarative-code-3b0b44fa02) and multiple twitter threads, today's Infrustrature management lacks a few things I want:

* There needs to be a Language (unlike blobs of YAML flying around). Syntax, semantics, grammar, types, rules, etc. When looking at something, a format definition tells you 
* Language should be Declarative
* Language should not be Turing complete.
* Language cannot be Regular
* Shouldn't drop you onto the lower machine. We don't write Javascript programs, and then debug in Assembly, while fully understanding how each construct of Javascript compiles into Machine code.
* Manifestation is context sensitive (programs have a flow or order, top-down.) It means reordering statements can change the result.

# Enter PreStruct

PreStruct is a manifestation programming language bounded at Second Order Predicate Logic with the following properties:
* It is not a code-generator or M4/C/expansion-style Macro expander. It doesn't generate code, instead it directly Manifests.
* It is context-free and unordered: types, facts, predicates and relations can be in any order, and they resolve to the same program.
* Is completely Declaractive
* Is a proper language

# The Language Specification

Note that the intent of the language is not efficiency, but efficacy. Even with literally "Millions of Machines", infrastructure composition does not need high-efficiency machine-level optimization. Types are chosen for ease of use, ease of understanding and ease of predictability.

## Types

### Simple Types

* string := Arbitrary string of characters
* number := Base-10 number of arbitrary precision
* time := Stores a point in time

### Maps

The only structure supported is a Map.

* map := a Key-Value mapping of any arbitrary type (other maps included) to any arbitrary type (other maps included).

### Other types

Inverting the premise of Lisp, all complex types are "maps" in PreStruct. A "List" may be emulated by having arbitrary keys in the map and iterating over the values. Ordered lists can iterate over values based on some ordering of their keys.

More complex types are defined through Predicates and Classification.

## Predicates

### 
