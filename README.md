# PreStruct
Second Order *Pre*dicate-Logic Infra*struct*ure: Infrastructure as Code
+ Declarative Infrastructure.

# The problem

After a [blog post](https://medium.com/@archisgore/can-we-just-cut-to-infrastructure-as-declarative-code-3b0b44fa02)
and multiple twitter threads, today's Infrustrature management
lacks a few things I want:

* There needs to be a *Language* (unlike blobs of YAML flying around).
    With Syntax, semantics, grammar, types, rules, etc.
* The Language should be Declarative and not Turing complete.
* The Language should apply to Infrastructure itself, meaning it must
    understand it has real-world side-effects and it operates
    in a real-world context. A language that generates a format for
    consumption by something else isn't good enough.
* Side-effects cannot be context-sensitive. Imperative
    languages or even Declarative languages like CSS change the outcome
    depending on what order the statements are interpreted in.
    Infrastructure is not inherently ordered, but it can be dependant.
    * This suggests a good language understands dependencies, but not
        textual ordering.
* Immutable infrastructure has one large obvious blind-spot:
    Existing/Current State is not an input into new state declaration.
    Declaring what you want isn't enough. That declaration needs
    context of when it was made.

# Enter PreStruct

PreStruct is a manifestation programming language bounded at
Second Order Predicate Logic with the following properties:
* Not a code-generator or M4/C/expansion-style Macro expander.
* It is context-aware: The real-world context
    in which it operates, and the real-world consequenes it creates
    are acknowledged. Forgeting to declare a database in the new
    revision thereby deleting it, for instance, is not left
    as an exercise to the user.
* It is not detached from actuation. It does not create a
    cloud-formation or Kubernetes YAML blob that is your problem
    to use as you see fit, and debug/maintain/manage.
* Is Declarative, but not Static. You Declare what you Want:
    "A Secure WebService" and get what you want: "A Secure WebService".
    * Nobody really wants 50 containers, 30 of them
    with side-cars, 20 load-balancers, 3 certs, 5 DNS configs for Let's
    Encrypt, 10 secret stores, etc. etc. That's never what you want.
    * What makes PreStruct unique is that it can tell you if you
    cannot get what you want, and why. Whether a commitment failed,
    or a manifestation is impossible given the constraints, etc.

# The PreStruct Language Specification

At the top level, there are four Primitives the language provides:
1. Desires - Declaration of the world as you would like it to be
2. Facts - Declaration by world as it is
3. Relations - Declaration of Desires/Facts relate to other Desires/Facts.
4. Commitments - Declarations of two commitments by
    Vendors/Cloud Providers/Operators:
    * Commitment to manifest a Desire into Fact, and when not possible,
    the commitment to tell you why not possible.
    * Commitment to tell you all the Facts as they know them.

Commitments are special in that they are available and visible within
PreStruct but not defined/writte/coded/programmed/implemented within it.
They are out-of-band side-effect creators as well as context-providers.

They are the eyes and ears of PreStruct.

## Dependency-Aware and Unordered

One notable feature of PreStruct is it is dependency-aware and
unordered. Desires, Facts and Relations can be present in any order in
the program, and the side-effects are guaranteed to be exactly
the same.

This is a conscious decision to promote ownership of rules, desires and
facts.

For example, it is possible a Developer provides an HTTP-fronted
web-service *Fact*, and InfoSec may express a *Desire* to expose it to
the Internet behind HTTPS. How and where each of them declare their
Relations doesn't change what gets exposed to the internet.

## Second-Order Relations

Occasionally we need Relations that Relate Relations, hence they are
called Second-Order Relations.

The main use-case for Second Order Relations is to import Relations
and Commitments from "libraries".


--------------------

TBD - Everything below this is a draft

## Types

### Simple Types

* string := Arbitrary string of characters
* number := Base-10 number of arbitrary precision
* time := Stores a point in time

### Data Structures/Types/Containers

The only structure supported is a Map.

* map := a Key-Value mapping of any arbitrary type (other maps included) to any arbitrary type (other maps included).

All traditional "structures"

## Predicates

### 
