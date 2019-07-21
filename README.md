# prestruct
*Pre*dicate-Logic Infra*struct*ure: Infrastructure defined through Propositional and Second Order Predicate Logic (SOPL).

# The problem

After a [blog post](https://medium.com/@archisgore/can-we-just-cut-to-infrastructure-as-declarative-code-3b0b44fa02) and multiple twitter threads discussing, it was clear that Infrustrature definition and management needs a few things not available in any language/tool today.

* There needs to be a Language (unlike blobs of YAML flying around). Syntax, semantics, grammar, types, rules, etc. When looking at something, a format definition tells you 
* Language should be Declarative
* Language should not be Turing complete.
* Language cannot be Regular
* Language shouldn't drop you onto the lower machine. We don't write Javascript programs, and then debug in Assembly, while fully understanding how each construct of Javascript compiles into Machine code. We certain

PreStruct is a programming language bounded at Second Order Predicate Logic that has the following properties:
* Language is Context-Free (Right above Regular, but right below Context-Sensitive), so it is complex enough to be useful, and no more complex than that.
* It is not a code-generator or M4/C/expansion-style Macro expander. It doesn't generate code that is then fed into your system. Logically, there is no YAML or CloudFormation behind the scenes.
  

# UX


# Notable Benefits (How is this simpler? How is this better?)

# What problem am I solving?
