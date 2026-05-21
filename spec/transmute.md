
# Transmute — System of Nature Transformation

> *"The alchemist does not destroy lead to obtain gold—he liberates it from its temporary form."*

---
## Concept

In Mythus, `transmute` is the act of manifesting a value under a different nature without altering its original essence. Inspired by alchemical transmutation, a transmuted value is neither destroyed nor copied—it is **revealed** in another form.

A `census` transmuted into `apeiron` remains the same value, now manifested in the continuous realm. The transmutation is temporary and explicit—the original value does not change.

---
## General Syntax

```mythus
value (transmute destination_type)
```

### Inside a truth source

```dogma
truth source {
	census a ^ apeiron b:
	a (transmute apeiron) + 0.1 > b
}
```

### Outside a truth source

```mythus
mortal census age = 30
mortal apeiron ageFloat = age (transmute apeiron)

proclaim(ageFloat) § 30.0
```
---

## Default Transmutations

The following transmutations are defined in the core of the language and **cannot be modified or overridden** by any `truth source`. They are the immutable order of the type system.

| Source | Destination | Behavior |
|-------------|--------------|-------------------------------------------------------|
`census` | `apeiron` | Integer to floating point — `5` → `5.0` |
`census` | `chronicle` | Integer to text — `5` → `"5"` |
`monad` | `census` | Positive to integer — `3` → `3` |
`monad` | `apeiron` | Positive to floating point — `3` → `3.0` |
`monad` | `chronicle` | Positive to text — `3` → `"3"` |
`apeiron` | `census` | Float to integer — truncates decimals `3.9` → `3` |
`apeiron` | `chronicle` | Float to text — `3.14` → `"3.14"` |
`rune` | `chronicle` | Character to text — `'A'` → `"A"` |
`rune` | `census` | Character to its numeric value — `'A'` → `65` |
`chronicle` | `legion` | Text to rune collection |

### Protecting default transmutations

Attempting to override a default transmutation in a `truth source` results in a compilation error:
```
⛧ Ragnarök: transmute census -> apeiron is a primordial transmutation.

Not even the dogma can alter the fundamental order — line 12.
```

---

## Custom Transmutations

The programmer can declare transmutations for their own types within the `truth source` of the `.dogma`. These coexist with the default transmutations without interfering with them.


### Declaration

```dogma
truth source {
	§{ Transmutation of a proper type to a primitive }§
	transmute objectPickle -> apeiron:
		ascend self.length

	§{ Transmutation of a proper type to another proper type }§
	transmute objectPickle -> objectCetriol:
		ascend summon objectCetriol(self.length, self.color)

	§{ Transmutation with conditional logic }§
	transmute objectTemperature -> yanantin:
		apu (self.degrees > 37.0) {
			ascend kay
		} ukhu {
			ascend mana
		} bard {
			ascend tinkuy
		}
}
```
---
### Usage in code
```mythus
mortal objectPickle pickle = summon objectPickle(15.3, "green")

§ Transmutation to primitive
mortal apeiron length = pickle (transmute apeiron)

§ Transmutation to another proper type
mortal objectCetriole cetriole = pickle (transmute objectCetriole)

§ Transmutation to yanantin - useful in truth source
mortal yanantin state = temperature (transmute yanantin)
```

---

## Transmute within Truth Source

When `transmute` is used within a `truth source` rule, the transmutation is **local to the evaluation** — the original value does not change in the cloister where it was declared.


```dogma
§ .dogma
truth source {
	§{ 
		When comparing a Pickle object to an apeiron,
		transmute the pickle's length to operate in the continuous domain
	}§
	Pickle object a ^ apeiron b:
		a (transmute apeiron) ± 0.1 == b

	§{
		When comparing a census to an apeiron,
		the census manifests as an apeiron only during evaluation
	}§
	census a ^ apeiron b:
		a (transmute apeiron) + 0.1 > b
}
```

```mythus
§ .myth
mortal Pickle object p = summon Pickle object(15.3, "green")
mortal apeiron measure = 15.25

§ Uses the truth source — p is transmuted internally during evaluation
§ The value of p does not change after the apu
apu (p == measure) {
	proclaim("The pickle matches the measure.")
} ukhu {
	proclaim("It doesn't match.")
} bard {
	§ undefined zone — re-evaluates
	mortal apeiron adjustedMeasure = measure + 0.05
	§ automatic runtime re-evaluation
}
```

---

## System Rules
1. **Default transmutations are immutable**: no `.dogma` file can override them.

2. **Custom transmutations apply only to custom types**: they cannot be declared for primitive language types.

3. **Transmutation in the truth source is local**: it does not modify the value in the active cluster.

4. **Explicit transmutation in code does produce a new value**:  the original value remains unchanged.

5. **If no declared transmutation exists for a type combination**, the compiler emits:

```
⛧ Ragnarök: no transmutation exists for object Pickle -> monad.
Declare the transmutation in the .dogma file — line 47.
```

---

## Scope Summary

| Context | Who can declare | Can modify defaults |
|---|---|---|
| Default transmutations | Core language | ✖ Never |
| Custom type transmutations | Programmer in `.dogma` | ✖ Not applicable |
| Local transmute in truth source | Programmer in `.dogma` | ✖ Never |
| Explicit transmute in `.mythus` | Programmer | ✖ Only use what is declared |
