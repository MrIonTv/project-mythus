# Especificación del Lenguaje Mythus 𓂀

---

## Introducción y Propósito

Mythus es un lenguaje de programación esotérico, compilado, de tipado estático y fuerte, inspirado en las tradiciones religiosas y mitológicas del mundo. Su propósito es demostrar que la abstracción computacional puede coexistir con un léxico simbólico profundo, donde cada palabra reservada carga significado más allá de su función sintáctica.

El código en Mythus no se escribe, se **declara**, se **consagra** y se **ejecuta** como un rito.

El lenguaje opera sobre dos tipos de archivo que trabajan en conjunto obligatorio:

- `.dogma` — la ley. Define constantes, visibilidad y contratos.
- `.mythus` — el mundo. Define clases, lógica e implementación.

---

## Modelo Computacional

Mythus es:

- **Compilado**: el código fuente se transforma a bytecode JVM antes de su ejecución.
- **Imperativo**: las instrucciones se ejecutan secuencialmente dentro de cloisters.
- **Con alcance léxico (estático)**: la visibilidad de los símbolos se resuelve en tiempo de compilación.
- **Con memoria semi-automática**: el manejo de memoria se apoya en el recolector de basura de la JVM. El programador no gestiona memoria manualmente salvo en casos explícitos.
- **Orientado a objetos**: toda entidad del programa es un `order` (clase).

**Justificación de Turing-completitud:**

1. Variables mutables (`mortal`)
2. Control condicional (`creed` / `heresy`)
3. Iteración potencialmente infinita (`samsara`)
4. Funciones con recursión permitida (`pray`)
5. Memoria estructurada (campos de `order`, colecciones)

---

## Sistema de Tipos

El sistema de tipos es estático y explícito:

- Todo identificador debe declarar su tipo.
- No existe inferencia de tipos.
- No existen conversiones implícitas.
- El cast explícito es responsabilidad del programador cuando corresponda.

### Tipos Primitivos

| Tipo Mythus | Equivalente          | Tradición            |
|-------------|----------------------|----------------------|
| `census`    | Entero               | Romana / Bíblica     |
| `monad`     | Positivo             | Pitagorica           |
| `apeiron`   | Float / Double       | Griega / Anaximandro |
| `kay`       | Boolean verdadero    | Quechua              |
| `mana`      | Boolean falso        | Quechua              |
| `tinkuy`    | Booleano desconocido | Quechua              |
| `rune`      | Char                 | Nórdica              |
| `chronicle` | String               | Medieval             |
| `nihil`     | null                 | Budista / Latina     |

### Mutabilidad

| Keyword   | Significado              | Tradición  |
|-----------|--------------------------|------------|
| `eternal` | Constante (val / const)  | Universal  |
| `mortal`  | Variable mutable (var)   | Universal  |

Una variable `mortal` no inicializada produce un error en su primer uso. Toda constante `eternal` debe inicializarse en el punto de declaración.

### Colecciones

| Tipo Mythus    | Equivalente          | Tradición          |
|----------------|----------------------|--------------------|
| `legion`       | Array                | Romana / Cristiana |
| `congregation` | List                 | Cristiana          |
| `covenant`     | Map / Diccionario    | Hebrea             |
| `trinity`      | Tupla de 3 elementos | Cristiana          |

### Tipo ausente

`abyss` representa la ausencia de valor de retorno (equivalente a `void`). Su uso es obligatorio como tipo de retorno cuando una función no retorna valor.

---

## El Sistema de Cisma (.dogma / .mythus)

### El archivo `.dogma`

El `.dogma` es la **ley**. Define:

- Todas las constantes (`eternal`) que el programa puede usar.
- La visibilidad pública de las clases declaradas en `.mythus`.
- Los contratos que las clases deben cumplir.
- La jerarquía de doctrina mediante herencia entre dogmas.

Una clase declarada en `.mythus` es **privada por defecto**. Solo lo que el `.dogma` marque como `reveal` se vuelve accesible desde el exterior.

```dogma
§ temple.dogma
eternal chronicle LANG_NAME = "Mythus"
eternal census    VERSION   = 1

reveal order Temple
conceal order Crypt
```

### El archivo `.mythus`

El `.mythus` es el **mundo**. Contiene:

- Declaración e implementación de clases (`order`).
- Una clase de entrada opcional marcada como `rite`.
- Toda la lógica, estado y comportamiento del programa.

```mythus
§ temple.mythus
order Temple {
    mortal chronicle name

    genesis(chronicle name) {
        self.name = name
    }

    reveal chronicle getName() {
        ascend self.name
    }
}
```

### Jerarquía de Dogmas — Herencia de Doctrina

Un `.dogma` puede invocar a otros dogmas como hijos, estableciendo una jerarquía de doctrina. Los hijos heredan los `eternal` del padre y pueden extender o redefinir visibilidad.

```dogma
§ abrahamic.dogma — dogma padre
eternal chronicle ORIGIN = "Abraham"
reveal order Prophet

§ islamic.dogma — hijo de abrahamic.dogma
invoke abrahamic
eternal chronicle HOLY_BOOK = "Quran"
eternal census    PILLARS   = 5
reveal order Mosque

§ jewish.dogma — hijo de abrahamic.dogma
invoke abrahamic
eternal chronicle HOLY_BOOK    = "Torah"
eternal census    COMMANDMENTS = 613
reveal order Synagogue
```

---

## El Sistema de Cisma — Divergencia de Mitos

El cisma modela cómo un mismo concepto existe en múltiples tradiciones con comportamiento distinto. Es el mecanismo de polimorfismo central del lenguaje.

### Dogma Primordial

Un `primordial` declara un concepto universal — un contrato que toda tradición reconoce pero ninguna posee completamente.

```dogma
§ soul.dogma
primordial Soul {
    eternal chronicle name
    abyss transcend()
    abyss judge()
}
```

### Schism — La Interpretación

Un `schism` hereda de un `primordial` y provee su propia verdad. Cada tradición implementa el concepto a su manera.

```dogma
§ buddhist.dogma
schism BuddhistSoul proceeds Soul {
    eternal census cycles = 6
    reveal abyss transcend()
    conceal abyss judge()
}

§ christian.dogma
schism ChristianSoul proceeds Soul {
    eternal chronicle afterlife = "heaven"
    reveal abyss transcend()
    reveal abyss judge()
}
```

### Doctrine — La Tradición Activa

El programador declara qué interpretación gobierna la ejecución mediante `doctrine`:

```dogma
§ main.dogma
doctrine buddhist
```

El código en `.mythus` opera sobre el `primordial` sin conocer el `schism` activo. El comportamiento cambia según la doctrina — igual que el mismo mito toma formas distintas según la fe que lo narra.

```mythus
§ ceremony.mythus
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

### Visibilidad en Dogmas

| Keyword      | Significado                              | Tradición        |
|--------------|------------------------------------------|------------------|
| `reveal`     | Público — visible desde fuera del dogma  | Gnóstica         |
| `conceal`    | Privado — interno a la implementación    | Gnóstica         |
| `veiled`     | Protegido — visible solo en jerarquía    | Islámica / Judía |
| `apocryphal` | Internal — visible en el canon, no fuera | Cristiana        |
| `sacred`     | Solo lectura pública                     | Universal        |

---

## Keywords y Vocabulario Religioso

### Declaración y Estructura

| Keyword      | Rol                          | Tradición              |
|--------------|------------------------------|------------------------|
| `primordial` | Interfaz / clase abstracta   | Universal              |
| `schism`     | Implementación concreta      | Cristiana              |
| `doctrine`   | Tradición activa             | Cristiana              |
| `canon`      | Módulo / paquete             | Cristiana / Islam      |
| `scripture`  | Constantes globales          | Universal              |
| `tome`       | Librería externa importada   | Ocultismo              |
| `codex`      | Clase sellada                | Medieval Cristiana     |
| `relic`      | Objeto inmutable             | Cristiana / Budista    |
| `sigil`      | Identificador especial       | Ocultismo              |
| `mantra`     | Constante de string          | Hindu / Budista        |
| `glyph`      | Tipo enumerado               | Egipcia / Maya         |

### Herencia y Relaciones

| Keyword    | Rol                                 | Tradición        |
|------------|-------------------------------------|------------------|
| `begets`   | Herencia (extends)                  | Cristiana/Hebrea |
| `emanates` | Herencia múltiple / mixin           | Neoplatónica     |
| `proceeds` | Implementa interfaz                 | Trinitaria       |
| `covenant` | Contrato obligatorio entre clases   | Hebrea           |
| `ordained` | Método abstracto obligatorio        | Cristiana        |
| `apostate` | Override explícito (rompe al padre) | Universal        |

### Control de Flujo

| Keyword      | Equivalente      | Tradición           |
|--------------|------------------|---------------------|
| `apu`        | if               | Andina              |
| `ukhu`       | else             | Andina / Quechua    |
| `bardo`      | else para tinkuy | Budismo Tibetano    |
| `samsara`    | while            | Budista / Hindu     |
| `pilgrimage` | for              | Islam / Cristiana   |
| `ascend`     | return           | Universal           |
| `exodus`     | break            | Hebrea              |
| `persist`    | continue         | Budista             |
| `pantheon`   | switch / when    | Griega / Romana     |
| `avatar`     | case             | Hindu               |
| `curse`      | throw            | Universal/Ocultismo |
| `ordeal`     | try              | Universal           |
| `absolution` | catch            | Cristiana           |
| `amen`       | finally          | Universal           |

### Clases y Objetos

| Keyword       | Rol                           | Tradición            |
|---------------|-------------------------------|----------------------|
| `order`       | Clase concreta                | Cristiana / Masónica |
| `summon`      | Instanciar objeto (new)       | Ocultismo            |
| `self`        | Referencia al objeto actual   | Budista              |
| `divine`      | Pertenece a la clase (static) | Universal            |
| `genesis`     | Constructor                   | Cristiana / Hebrea   |
| `requiem`     | Destructor / cleanup          | Cristiana            |
| `creed`       | Interfaz pura                 | Cristiana            |
| `idol`        | Singleton / object            | Universal            |
| `reformation` | Override de método            | Cristiana            |

### Módulos e Imports

| Keyword     | Equivalente | Tradición  |
|-------------|-------------|------------|
| `invoke`    | import      | Ocultismo  |
| `preach`    | export      | Cristiana  |
| `diocese`   | namespace   | Cristiana  |
| `monastery` | package     | Budista    |

### Concurrencia

| Keyword     | Equivalente  | Tradición   |
|-------------|--------------|-------------|
| `prophecy`  | async        | Universal   |
| `vigil`     | await        | Cristiana   |
| `spirit`    | thread       | Universal   |
| `communion` | sync         | Cristiana   |
| `seal`      | mutex / lock | Apocalipsis |

### Miscelánea

| Keyword      | Equivalente        | Tradición |
|--------------|--------------------|-----------|
| `proclaim`   | print              | Universal |
| `testament`  | assert             | Hebrea    |
| `confession` | debug mode         | Cristiana |
| `rite`       | main / entry point | Universal |
| `specter`    | lambda             | Ocultismo |
| `stigma`     | annotation         | Cristiana |
| `forsaken`   | deprecated         | Universal |

---

## Glossae — Comentarios

En la tradición latina medieval, una *glossa* era una anotación escrita al margen de un manuscrito sagrado — la voz del escriba hablando fuera del texto canónico. En Mythus, las glossae son ignoradas por el compilador pero preservadas para quien lea la escritura después.

### Glossa de verso único

Comienza con `§` y se extiende hasta el final de la línea.

```mythus
§ Este order representa el ciclo eterno del renacimiento
order Samsara {
    mortal census cycles = 0
}
```

### Codex Glossa (bloque)

Abre con `§{` y cierra con `}§`. Puede abarcar múltiples versos.

```mythus
§{
    El campo cycles registra cuántas veces
    este alma ha completado el ciclo desde su genesis.
    Máximo permitido: 6 reinos del samsara budista.
}§
mortal census cycles = 0
```

---

## Manejo de Memoria

Mythus utiliza un modelo de memoria **semi-automático** apoyado en el recolector de basura de la JVM:

- Los objetos creados con `summon` son gestionados automáticamente.
- La memoria se libera cuando ningún símbolo del cloister activo referencia al objeto.
- No existe aritmética de punteros ni liberación manual de memoria.
- En caso de ciclos de referencia complejos, el compilador emite una advertencia en tiempo de compilación.

El programador puede sugerir la liberación explícita de un objeto mediante `requiem`, aunque el compilador no garantiza el momento exacto de la liberación:

```mythus
order Shrine {
    requiem() {
        §{ limpieza de recursos externos }§
        proclaim("El santuario ha sido clausurado.")
    }
}
```

---

## Control de Flujo

```mythus
§ Condicional
oracle (souls > 5) {
    proclaim("La congregación es digna.")
} heresy {
    proclaim("La congregación es insuficiente.")
}

§ Ciclo while
mortal census count = 3
cycle (count > 0) {
    proclaim("Cantando... " + count)
    count = count - 1
}

§ Ciclo for
pilgrimage (mortal census i = 0; i < 7; i++) {
    proclaim("Día de la creación: " + i)
}

§ Pattern matching
mortal chronicle faith = "norse"
pantheon (faith) {
    avatar "norse"    => proclaim("Salve Odín, el Allfather.")
    avatar "egyptian" => proclaim("Gloria a Ra, señor del sol.")
    avatar "hindu"    => proclaim("Om Namah Shivaya.")
}
```

---

## Funciones y Clases

### Declaración de clase

```mythus
order Deity {
    mortal chronicle title

    genesis(chronicle title) {
        self.title = title
    }

    reveal abyss descend() {
        proclaim("La deidad " + self.title + " camina entre mortales.")
    }
}
```

### Herencia

```mythus
order Demigod begets Deity {
    mortal chronicle mortalParent

    genesis(chronicle title, chronicle mortalParent) {
        self.title = title
        self.mortalParent = mortalParent
    }

    reformation abyss descend() {
        proclaim("El semidiós " + self.title + ", hijo de " + self.mortalParent + ", desciende.")
    }
}
```

### Funciones anónimas — Specter

```mythus
mortal specter bless = (chronicle name) => {
    ascend "Que " + name + " encuentre paz."
}

proclaim(bless("el errante"))
```

### Punto de entrada

El programa inicia en el bloque `rite`. Su existencia es opcional — si no está presente, el compilador no genera un ejecutable independiente.

```mythus
rite {
    mortal Demigod hero = summon Demigod("Hercules", "Alcmene")
    hero.descend()
}
```

### Manejo de excepciones

```mythus
order SacredRitual {
    reveal abyss perform(census energy) {
        ordeal {
            oracle (energy <= 0) {
                curse "NotEnoughEnergyException"("El ritual requiere más energía.")
            }
            proclaim("El ritual es exitoso.")
        } absolution (NotEnoughEnergyException e) {
            proclaim("El ritual falló: " + e.message)
        } amen {
            proclaim("El altar queda limpio sin importar el resultado.")
        }
    }
}
```

---

> Se puede ver mayor información en spec/keywords.md