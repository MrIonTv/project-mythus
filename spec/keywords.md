# Mythus Keyword Repertoire

> All religious, mythological, and spiritual traditions are valid sources.
> Every keyword carries meaning beyond syntax — it carries doctrine.

---

## Declaration & Structure

| Keyword      | Tradition            | Suggested Role                          |
|--------------|----------------------|-----------------------------------------|
| `primordial` | Universal            | Interface / abstract class              |
| `schism`     | Christian            | Concrete implementation of a primordial |
| `dogma`      | Christian / Islam    | Constants and contracts file            |
| `mythus`     | Greco-Roman          | Implementation file                     |
| `doctrine`   | Christian            | Active tradition declaration            |
| `canon`      | Christian / Islam    | Module or package                       |
| `scripture`  | Universal            | Read-only file / global constants       |
| `tome`       | Occultism            | Imported external library               |
| `codex`      | Medieval Christian   | Sealed class                            |
| `relic`      | Christian / Buddhist | Immutable object                        |
| `vessel`     | Universal            | Variable / value container              |
| `sigil`      | Occultism            | Special symbol / identifier             |
| `mantra`     | Hindu / Buddhist     | String constant                         |
| `glyph`      | Egyptian / Mayan     | Enumerated type                         |

---

## Visibility

| Keyword      | Tradition        | Suggested Role                                   |
|--------------|------------------|--------------------------------------------------|
| `reveal`     | Gnostic          | public                                           |
| `conceal`    | Gnostic          | private                                          |
| `veiled`     | Islamic / Jewish | protected                                        |
| `apocryphal` | Christian        | internal (visible within the canon, not outside) |
| `sacred`     | Universal        | public read-only                                 |
| `profane`    | Universal        | unrestricted access (public static)              |

---

## Inheritance & Relationships

| Keyword    | Tradition          | Suggested Role                             |
|------------|--------------------|--------------------------------------------|
| `begets`   | Christian / Hebrew | inheritance (extends)                      |
| `emanates` | Neoplatonic        | multiple inheritance / mixin               |
| `proceeds` | Trinitarian        | implements interface                       |
| `covenant` | Hebrew             | mandatory contract between two classes     |
| `ordained` | Christian          | must-be-overridden method (abstract)       |
| `stele`    | Greek / Egiptian   | final / non-overridable                    |
| `apostate` | Universal          | explicit override (breaks from the parent) |

---

## Control Flow

| Keyword      | Tradition             | Suggested Role                        |
|--------------|-----------------------|---------------------------------------|
| `pray`       | Universal             | function call / invocation            |
| `creed`      | Christian             | conditional (if)                      |
| `heresy`     | Christian / Greek     | alternative branch (else)             |
| `samsara`    | Buddhist / Hindu      | while loop                            |
| `pilgrimage` | Islam / Christian     | for loop (journey with a destination) |
| `ascend`     | Universal             | return value                          |
| `nirvana`    | Buddhist              | break out of control flow             |
| `persist`    | Buddhist              | next iteration (continue)             |
| `crossroads` | Greek / Roman         | switch / when                         |
| `path`       | Greek / Roman         | each case in the crossroads           |
| `anathema`   | Greek / Roman         | default case in the crossroads        |
| `curse`      | Universal / Occultism | throw exception                       |
| `ordeal`     | Universal             | try block                             |
| `absolution` | Christian             | catch exception                       |
| `amen`       | Universal             | finally block                         |

---

## Data Types

| Keyword        | Tradition              | Suggested Role         |
|----------------|------------------------|------------------------|
| `soul`         | Universal              | generic object / Any   |
| `abyss`        | Gnostic / Lovecraftian | void                   |
| `truth`        | Universal              | Boolean true           |
| `heresy`       | Christian              | Boolean false          |
| `eternal`      | Universal              | constant (val / const) |
| `mortal`       | Universal              | mutable variable (var) |
| `rune`         | Norse                  | char / character       |
| `chronicle`    | Medieval               | String                 |
| `census`       | Roman / Biblical       | Int                    |
| `cubit`        | Hebrew / Egyptian      | Float / Double         |
| `legion`       | Christian / Roman      | Array / collection     |
| `congregation` | Christian              | List                   |
| `covenant`     | Hebrew                 | Map / dictionary       |
| `trinity`      | Christian              | Three-element tuple    |

---

## Classes & Objects

| Keyword    | Tradition           | Suggested Role                                  |
|------------|---------------------|-------------------------------------------------|
| `order`    | Christian / Masonic | concrete class                                  |
| `summon`   | Occultism           | instantiate object (new)                        |
| `self`     | Buddhist            | reference to current object (this)              |
| `nihil`    | Buddhist / Latin    | absence of value (null)                         |
| `divine`   | Universal           | belongs to the class, not the instance (static) |
| `genesis`  | Christian / Hebrew  | constructor                                     |
| `requiem`  | Christian           | destructor / cleanup                            |
| `pantheon` | Greek               | enumeration (enum)                              |
| `idol`     | Universal           | singleton / object declaration                  |

---

## Modules & Imports

| Keyword     | Tradition            | Suggested Role              |
|-------------|----------------------|-----------------------------|
| `invoke`    | Occultism            | import module               |
| `preach`    | Christian            | export symbol               |
| `diocese`   | Christian            | namespace / module grouping |
| `monastery` | Buddhist / Christian | root package                |

---

## Concurrency

| Keyword     | Tradition              | Suggested Role   |
|-------------|------------------------|------------------|
| `prophecy`  | Universal              | async function   |
| `vigil`     | Christian              | await result     |
| `spirit`    | Universal              | execution thread |
| `communion` | Christian              | synchronization  |
| `seal`      | Occultism / Revelation | mutex / lock     |

---

## Miscellaneous

| Keyword       | Tradition          | Suggested Role              |
|---------------|--------------------|-----------------------------|
| `proclaim`    | Universal          | standard output (print)     |
| `oracle`      | Greek              | user input                  |
| `testament`   | Hebrew / Christian | assertion                   |
| `confession`  | Christian          | debug mode                  |
| `rite`        | Universal          | program entry point (main)  |
| `specter`     | Occultism          | anonymous function (lambda) |
| `stigma`      | Christian          | annotation / decorator      |
| `forsaken`    | Universal          | deprecated code             |
| `reformation` | Christian          | method override             |

# The Delimitation
Code blocks in Mythus are called **cloisters**, delimited by `{` and `}`. 
Haven't found the traditional origin yet.

Statements in Mythus are called **verse** is the minimal unit of executable doctrine in Mythus.
Each verse occupies its own line. No terminator symbol is required,
the end of the line consecrates the end of the verse. From Christian origin.

# Glossae

A **glossa** is a marginal annotation — the voice of the scribe speaking
outside the canonical text. In Mythus, glossae are ignored by the compiler
but preserved for those who read the scripture after you.

### Single-verse glossa
Begins with `§` and extends to the end of the line.

### Codex glossa
Opens with `§{` and closes with `}§`. Spans multiple verses.

# Mythus — Code Examples

> *"In the beginning was the Verb, and the Verb compiled."*

These examples are not meant to be exhaustive — they are **rituals**.
Each one demonstrates the language breathing its doctrine into form.

---

## 1. Hello World

The simplest rite. A single proclamation to the world.

```dogma
// hello.dogma
eternal chronicle SALUTATION = "Mythus"
```
```mythus
// hello.mythus
order Greeting {
    genesis() {
        proclaim(SALUTATION)
    }
}

rite {
    summon Greeting()
}
```

---

## 2. Constants & Variables

`eternal` values are bound at compile time inside `.dogma`.
`mortal` values may change throughout execution.

```dogma
// world.dogma
eternal chronicle LANGUAGE_NAME = "Mythus"
eternal census    VERSION       = 1
eternal truth     IS_ESOTERIC   = truth
```

```mythus
// world.mythus
rite {
    mortal census age = 0
    age = age + 1
    proclaim(age)
    proclaim(LANGUAGE_NAME)
}
```

---

## 3. Classes & Visibility

A class declared in `.mythus` is private by default.
Only what the `.dogma` `reveal`s becomes accessible.

```dogma
// temple.dogma
reveal order Temple
conceal order Crypt
```

```mythus
// temple.mythus
order Temple {
    mortal chronicle name

    genesis(chronicle name) {
        self.name = name
    }

    reveal chronicle getName() {
        ascend self.name
    }
}

order Crypt {
    // only accessible within this .mythus
    mortal census depth = 4
}
```

---

## 4. Inheritance — begets

A child order inherits nature and behavior from its parent.

```dogma
// beings.dogma
reveal order Deity
reveal order Demigod
```

```mythus
// beings.mythus
order Deity {
    mortal chronicle title

    genesis(chronicle title) {
        self.title = title
    }

    reveal abyss descend() {
        proclaim("The deity " + self.title + " walks among mortals.")
    }
}

order Demigod begets Deity {
    mortal chronicle mortalParent

    genesis(chronicle title, chronicle mortalParent) {
        self.title = title
        self.mortalParent = mortalParent
    }

    reformation abyss descend() {
        proclaim("The demigod " + self.title + " born of " + self.mortalParent + " descends.")
    }
}

rite {
    mortal Deity god        = summon Deity("Zeus")
    mortal Demigod halfblood = summon Demigod("Hercules", "Alcmene")

    god.descend()
    halfblood.descend()
}
```

---

## 5. The Schism System

The same concept — the soul — interpreted by different traditions.
The `.mythus` code does not change. The `doctrine` does.

```dogma
// soul.dogma — the universal concept
primordial Soul {
    eternal chronicle name
    abyss transcend()
    abyss judge()
}

// buddhist.dogma
schism BuddhistSoul proceeds Soul {
    eternal census cycles = 6
    reveal abyss transcend()
    conceal abyss judge()
}

// christian.dogma
schism ChristianSoul proceeds Soul {
    eternal chronicle afterlife = "heaven"
    reveal abyss transcend()
    reveal abyss judge()
}

// main.dogma
doctrine buddhist
```

```mythus
// ceremony.mythus
order Ceremony {
    mortal Soul soul

    genesis(Soul soul) {
        self.soul = soul
    }

    reveal abyss perform() {
        self.soul.transcend()
    }
}

rite {
    mortal Ceremony ritual = summon Ceremony(summon BuddhistSoul("Siddhartha"))
    ritual.perform()
}
```

---

## 6. Control Flow

```mythus
// judgment.mythus
rite {
    mortal census souls = 10

    // creed / heresy — conditional
    creed (souls > 5) {
        proclaim("The congregation is worthy.")
    } heresy {
        proclaim("The congregation is too small.")
    }

    // pilgrimage — for loop
    pilgrimage (mortal census i = 0; i < souls; i++) {
        proclaim("Soul number: " + i)
    }

    // samsara — while loop
    mortal census count = 3
    samsara (count > 0) {
        proclaim("Chanting... " + count)
        count = count - 1
    }
}
```

---

## 7. Pattern Matching — crossroads / path / anathema

```mythus
// tradition.mythus
rite {
    mortal chronicle faith = "norse"

    crossroads (faith) {
        path "norse"     => proclaim("Hail Odin, the Allfather.");
        path "egyptian"  => proclaim("Praise Ra, lord of the sun.");
        path "hindu"     => proclaim("Om Namah Shivaya.");
        path "greek"     => {
                            proclaim("Glory to Zeus, ruler of Olympus.")
                            proclaim("The lesser paths are easy to go, 
                            the cloisters shall leave trough the nirvana");
                            nirvana;
                            }
        anathema         => 
    }
}
```

---

## 8. Exception Handling

```mythus
// ritual.mythus
order SacredRitual {
    reveal abyss perform(census energy) {
        ordeal {
            oracle (energy <= 0) {
                curse "NotEnoughEnergyException"("The ritual requires more energy.")
            }
            proclaim("The ritual succeeds.")
        } absolution (NotEnoughEnergyException e) {
            proclaim("Ritual failed: " + e.message)
        } amen {
            proclaim("The altar is cleansed regardless.")
        }
    }
}

rite {
    mortal SacredRitual r = summon SacredRitual()
    r.perform(0)
}
```

---

## 9. Collections

```mythus
// pantheon.mythus
rite {
    // legion — array
    mortal legion gods = ["Odin", "Thor", "Freya", "Loki"]

    // congregation — list
    mortal congregation saints = summon congregation()
    saints.add("Francis")
    saints.add("Augustine")
    saints.add("Teresa")

    // covenant — map / dictionary
    mortal covenant temples = summon covenant()
    temples.set("Greece",  "Parthenon")
    temples.set("Egypt",   "Karnak")
    temples.set("India",   "Brihadeeswarar")

    proclaim(temples.get("Egypt"))
}
```

---

## 10. Async — prophecy / vigil

```mythus
// oracle.mythus
order ProphecyOracle {
    reveal prophecy chronicle seekTruth(chronicle question) {
        mortal chronicle answer = vigil fetchFromBeyond(question)
        ascend answer
    }

    conceal prophecy chronicle fetchFromBeyond(chronicle question) {
        // simulated async operation
        ascend "The answer to '" + question + "' is hidden in the stars."
    }
}

rite {
    mortal ProphecyOracle seer = summon ProphecyOracle()
    mortal chronicle vision    = vigil seer.seekTruth("What is the nature of existence?")
    proclaim(vision)
}
```

---

## 11. Dogma Hierarchy — child dogmas

A `.dogma` may have children, establishing a hierarchy of doctrine.

```dogma
// abrahamic.dogma — parent dogma
eternal chronicle ORIGIN = "Abraham"

reveal order Prophet
reveal order Scripture
```

```dogma
// islamic.dogma — child of abrahamic.dogma
invoke abrahamic

eternal chronicle HOLY_BOOK  = "Quran"
eternal chronicle PROPHET     = "Muhammad"
eternal census    PILLARS     = 5

reveal order Mosque
```

```dogma
// jewish.dogma — child of abrahamic.dogma
invoke abrahamic

eternal chronicle HOLY_BOOK  = "Torah"
eternal chronicle COVENANT    = "Sinai"
eternal census    COMMANDMENTS = 613

reveal order Synagogue
```

```mythus
// faith.mythus
order Mosque {
    reveal abyss pray() {
        proclaim("Allahu Akbar. The call to prayer echoes.")
    }
}

order Synagogue {
    reveal abyss pray() {
        proclaim("Shema Yisrael. The prayer rises.")
    }
}

rite {
    mortal Mosque    mosque    = summon Mosque()
    mortal Synagogue synagogue = summon Synagogue()

    mosque.pray()
    synagogue.pray()
}
```

---

## 12. Lambda — specter

```mythus
// shadow.mythus
rite {
    mortal specter bless = (chronicle name) => {
        ascend "May " + name + " find peace."
    }

    proclaim(bless("the wanderer"))
    proclaim(bless("the lost soul"))
}
```

---

> *Each program is a scripture. Each execution, a rite.*
> *Write not merely to instruct the machine, write to profess 
> your doctrine in the circuits.*