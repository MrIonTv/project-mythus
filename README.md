# Mythus 𓂀

> *"In the beginning was the Word, and the Word compiled."*

Mythus is an esoteric, statically-typed programming language inspired by the religious
and spiritual traditions of the world. Code is not merely written — it is **declared**, 
**consecrated**, and **executed** as ritual.

---

## The Two Sacred Files

### `.dogma`
The **law**. A `.dogma` file defines:
- All hardwired (compile-time constant) values the program may use
- The public surface of classes — a class declared in `.mythus` only becomes
  visible to the outside world if its `.dogma` marks it as such
- Inheritance between dogmas: a `.dogma` may have child dogmas, establishing
  a hierarchy of doctrine

#### The Schism System
Religious myths do not exist in a single form — the same concept diverges across
traditions, each interpreting the doctrine in its own way. Mythus reflects this
through the **Schism System**:

- A `primordial` dogma declares a universal concept: a contract that every
  tradition recognizes but none fully owns.
- A `schism` dogma inherits from a `primordial` and provides a concrete
  interpretation — its own truth.
- The active interpretation is declared via `doctrine` at the program level,
  determining which schism governs execution.
- Within a dogma, `reveal` exposes a member to the outside world.
  `conceal` keeps it internal to the tradition.

This means the same `.mythus` code can behave differently depending on which
doctrine is professed — just as the same myth takes different forms depending
on the faith that tells it.

```dogma
// soul.dogma — a concept all traditions recognize
primordial Soul {
    eternal name
    void transcend()
    void judge()
}

// buddhist.dogma — one tradition's interpretation
schism BuddhistSoul inherits Soul {
    eternal cycles = 6
    reveal transcend()
    conceal judge()
}
```

Think of `.dogma` as a mandatory covenant between your code and the world —
but a covenant that may be interpreted differently depending on who professes it.
### `.mythus`
The **world**. A `.mythus` file defines:
- Classes and their implementations
- An optional entry class (the ritual that begins execution)
- Business logic, state, and behavior

A `.mythus` class is **private by default**. Only what the `.dogma` consecrates becomes public.

---

## Philosophy

Keywords in Mythus are drawn from religious and spiritual traditions across the world:
Hindu, Christian, Islamic, Buddhist, Jewish, Norse, Egyptian, and more.
No single faith dominates — all traditions contribute equally to the language.

---

## Project Status

🔴 Early design phase — contributions and ideas welcome.

---

## Building

> Requires JDK 17+ and Gradle.

```bash
git clone https://github.com/MrIonTv/project-mythus.git
cd project-mythus
./gradlew build
```

---

## License

MIT License — free as in freedom, open as in scripture.
