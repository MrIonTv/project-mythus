
# Truth Source — Configurable Truth System

> *"Dogma doesn't invent truth—it defines where doubt ends and begins."*

---

## Concept

In Mythus, the evaluation of `kay` and `mana` works by default for all primitive types in the language. The `truth source` is a statement in the `.dogma` that **selectively** extends that behavior for specific combinations of types, incorporating fuzzy logic, tolerance thresholds, and custom transmutations.

The `truth source` doesn't replace the underlying logic—it **shapes** it where the programmer requires.


---

## Baseline Behavior — Always Present

Without any declared `truth source`, the language evaluates conditions with strict logic:

```mythus
mortal census a = 5
mortal census b = 3

apu (a == b) {
	proclaim("Equal.")
} ukhu {
	proclaim("Different.")
}
```

This behavior **never changes** regardless of what the `.dogma` declares.

---

## Truth Source Declaration

```dogma
truth source {
	§{ left_type a ^ right_type b : evaluation rules }§
	<type_A> a ^ <type_B> b:
		<evaluation expression>
}
```

The symbol `^` separates the two operands involved in the comparison. The order matters , `A ^ B` and `B ^ A` are distinct rules.

---

## Evaluation Zones

Each rule implicitly defines three zones for three-valued logic:

| Zone | State | Description |
|---|---|---|
| Within the declared range | `kay` | The condition is true |
| Outside the declared range | `mana` | The condition is false |
| At the threshold boundary | `tinkuy` | Undefined zone — gradient|

The compiler automatically calculates the `tinkuy` zone from the boundaries of the declared range. The programmer does not need to specify it, it emerges from the rule.

---

## Numerical Domains and Fuzzy Logic

Fuzzy logic only has semantic meaning in continuous domains:

### `apeiron` — continuous domain ✔
Between `3.0` and `4.0`, there is an infinite range of values. The `tinkuy` zone is a real gradient.

```
3.0 3.3 3.5 3.7 4.0
|--------|--------|--------|--------|
mana | tinkuy gradient | kay
```

### `census` — discrete domain ⚠ Between `3` and `5`, only `4` exists. The `tinkuy` on `census` is a point case, not a gradient.

```
3 4 5
|----|----|
mana |¿? | kay
```

The compiler emits a **⊕ Pachakuti** if a fuzzy range is declared over `census` with a window greater than `1` — this is not an error, but a warning that continuous logic is being applied to a discrete domain.

### `monad` — excluded from fuzzy logic ✖
The indivisible nature of the `monad` is incompatible with graduality. A `monad` cannot be "almost true". Declaring a fuzzy `truth source` on `monad` produces:

### `logos` — exact rational domain ✖
The exactness of `logos` makes fuzzy logic unnecessary.

`1/3 == 1/3` is always `kay` — no gradient, no `tinkuy`.
Declaring a `truth source` on `logos` produces:

⛧ Ragnarök: logos does not admit fuzzy logic, the exact ratio has no threshold - line <lineNumber>.

```
⛧ Ragnarök: monad does not admit fuzzy logic - its nature is indivisible - line <lineNumber>.
```

---

## Rule Syntax

### Symmetric Tolerance

```dogma
§ .dogma
truth source {
	apeiron a ^ apeiron b:
		a ± 0.5 == b

	§{
		kay : b within [a - 0.5, a + 0.5]
		mana : b outside the range
		tinkuy: b on the exact boundary of the threshold
	}
}
```

### Asymmetric Tolerance

```dogma
§ .dogma
truth source {
	apeiron a ^ apeiron b:
		a - 0.3 > b
		a + 0.7 < b

	§{
		kay : b between (a - 0.3) and (a + 0.7)
		mana: b outside that range
		tinkuy: b on the exact edges
	}§
}
```

### Proper Type vs. Primitive

```dogma
§ .dogma
truth source {
	pickleObject a ^ apeiron b:
		a.length +- 0.1 == b
}
```

### Local Cast with Transmute

```dogma
§ .dogma
truth source {
	census a ^ apeiron b:
		a (transmute apeiron) + 0.1 > b
}
```

### Proper Type vs. Proper Type

```dogma
§ .dogma
truth source {
	pickleObject a ^ pickleObject b:
		a.length +- 0.1 == b.length
}
```

---

## Transmutations in Truth Source

The programmer can declare Custom transmutations within the `truth source` for your own types. The language's default transmutations **cannot be redefined**.


```dogma
§ .dogma
truth source {
	§{ Transmutation of a proper type to a primitive }§
	transmute objectPickle -> apeiron:
		ascend self.length

	§{ Transmutation with conditional logic }§
	transmute objectTemperature -> yanantin:
		apu (self.degrees > 37.0) {
			ascend kay
		} ukhu {
			ascend mana
		} bardo {
			ascend tinkuy
		}

	§{ Using transmutation in a rule }§
	objectPickle a ^ apeiron b:
		a (transmute apeiron) +- 0.1 == b
}
```

---

## Propagation of Tinkuy in Logical Operators

When a compound condition with `&&` or `||` encounters a `tinkuy`, the propagation follows these Rules:

### AND (`&&`)

| Left | Right | Result | Reasoning |
|-----------|----------|-----------|-------------------------------------|
|`kay`     | `kay`    | `kay`    | Both true                                |
|`kay`     | `mana`   | `mana`   |The fake absorbs                          |
| `mana`   | `kay`    | `mana`   | The fake absorbs                         |
| `mana`   | `mana`   | `mana`   | Both false                               |
| `kay`    | `tinkuy` | `tinkuy` | Lack of definition spreads               |
| `tinkuy` | `kay`    | `tinkuy` | Lack of definition spreads               |
| `mana`   | `tinkuy` | `mana`   | The false absorbs the lack of definition |
| `tinkuy` | `mana`   | `mana`   | The false absorbs the lack of definition |
| `tinkuy` | `tinkuy` | `tinkuy` | Double indefinition                      |

### OR (`||`)

| Left | Right | Result | Reasoning |
|-----------|----------|-----------|-------------------------------------|
| `kay`   | `kay`    | `kay`    | Both true                                         |
|`kay`    | `mana`   | `kay`    | The true one absorbs in OR                        |
|`mana`   | `kay`    | `kay`    | The true one absorbs in OR                        |
|`mana`   | `mana`   | `mana`   | Both false                                        |
|`kay`    | `tinkuy` | `kay`    | The true one absorbs in OR                        |
|`tinkuy` | `kay`    | `kay`    | The true one absorbs in OR                        |
|`mana`   | `tinkuy` | `tinkuy` | The false one does not resolve the indefiniteness |
|`tinkuy` | `mana`   | `tinkuy` | The false one does not resolve the indefiniteness |
|`tinkuy` | `tinkuy` | `tinkuy` | Double indefiniteness                             |

---

## Behavior in Flow Control

```mythus
§ .myth
apu (<condition>) {
	§ executes if kay
} ukhu {
	§ executes if mana
} bardo {
	§ executes if tinkuy
	§ extra resolution steps
	§ the runtime re-evaluates the condition one last time upon exiting bardo
	§ if still in tinkuy → ⛧ Ragnarök
}
```

### Without bardo branch

If the result is `tinkuy` and there is no `bardo` branch:

```
⛧ Ragnarök : condition in tinkuy state without a bardo branch for resolution - line  <lineNumber>.
```

### With bardo branch

1. The `bardo` steps are executed
2. The runtime re-evaluates the original condition upon exiting
3. If it resolves to `kay` → Execute the `apu` block
4. If it resolves to `mana` → Execute the `ukhu` block
5. If it continues in `tinkuy` → **⛧ Ragnarök**

---

## Rule Precedence

When multiple rules can apply to the same type combination, the compiler applies the **first declared rule** that matches. The order in the `.dogma` is the order of precedence.


```dogma
truth source {
	§{ This rule applies first }§
	apeiron a ^ apeiron b:
		a ± 0.5 == b

	§{ This is never reached for apeiron ^ apeiron }§
	apeiron a ^ apeiron b:
		a ± 1.0 == b
}
```

The compiler emits an **𓂀 Augur** when it detects an unreachable rule:

```
𓂀 Augur : rule apeiron ^ apeiron on line <lineNumber> will never be reached - line <lineNumber>.
```

---

## Configuring Augurs in Truth Source

**𓂀 Augur** notifications can be configured as visible or silent from `.dogma`:

```dogma
§ .dogma

§ The augur speaks in the terminal for monad transcendence
reveal Augur transcendence

§ The augur remains silent for unreachable rules
```
---

## Scope Summary

| Capability | Allowed in truth source |
---|---|
| Define tolerance for proper types       | ✔ |
| Define tolerance for primitive types    | ✔ |
| Redefine default transmutations         | ✖ |
| Declare transmutations for proper types | ✔ |
| Modify the behavior of `&&` and `||`    | ✖ |
| Configure augur visibility              | ✔ |
| Exclude monad from fuzzy logic          | ✖ always excluded |
