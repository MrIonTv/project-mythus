# Mythus 𓂀
> 🌐 **Español** | [English](README.md)

> *"En el principio era el Verbo, y el Verbo compiló."*


Mythus es un lenguaje de programación esotérico de tipado estático, inspirado en las tradiciones religiosas y espirituales del mundo. El código no solo se escribe, sino que se **declara**,
**consagra** y **ejecuta** como un ritual.

---

## Los Dos Archivos Sagrados

### `.dogma`
La **ley**. Un archivo `.dogma` define:
- Todos los valores fijos (constantes en tiempo de compilación) que el programa puede usar.
- La superficie pública de las clases: una clase declarada en `.mythus` solo se vuelve
  visible para el mundo exterior si su archivo `.dogma` la marca como tal.
- Herencia entre dogmas: un archivo `.dogma` puede tener dogmas hijos, estableciendo
  una jerarquía de doctrinas.

#### El Sistema de Cismas
Los mitos religiosos no existen en una sola forma: el mismo concepto diverge entre
tradiciones, cada una interpretando la doctrina a su manera. Mythus refleja esto
a través del **Sistema de Cismas**:

- Un dogma `primordial` declara un concepto universal: un contrato que toda
  tradición reconoce, pero ninguna posee por completo.

- Un dogma `schism` (cismático) hereda de un dogma `primordial` y proporciona una interpretación concreta:
  su propia verdad.

- La interpretación activa se declara mediante `doctrine` a nivel de programa,
  determinando qué cisma rige la ejecución. 
- Dentro de un dogma, `reveal` expone a un miembro al mundo exterior.`conceal` lo mantiene dentro de la tradición.

Esto significa que el mismo código `.mythus` puede comportarse de manera diferente según la
doctrina que se profese, del mismo modo que un mismo mito adopta diferentes formas según
la fe que lo narra.

```dogma
// soul.dogma: un concepto que todas las tradiciones reconocen
primordial Alma {
    eternal nombre
    abyss transcend()
    abyss judge()
}

// buddhist.dogma: la interpretación de una tradición
schism BuddhistSoul begets Soul {
    eternal ciclos = 6
    reveal transcend()
    conceal judge()
}
```

Piensa en `.dogma` como un pacto obligatorio entre tu código y el mundo,
pero un pacto que puede interpretarse de manera diferente según quién lo profese.

### `.mythus`
El **mundo**. Un archivo `.mythus` define:
- Clases y sus implementaciones
- Una clase de entrada opcional (el ritual que inicia la ejecución)
- Lógica de negocio, estado y comportamiento

Una clase `.mythus` es **privada por defecto**. Solo lo que el archivo `.dogma` consagra se vuelve público.

--

## Filosofía

Las palabras clave en Mythus provienen de tradiciones religiosas y espirituales de todo el mundo:
hindú, cristiana, islámica, budista, judía, nórdica, egipcia y más.

Ninguna fe predomina; todas las tradiciones contribuyen por igual al lenguaje.

--

## Estado del proyecto

🔴 Fase inicial de diseño: se agradecen las contribuciones e ideas.

--

## Compilación

> Requiere JDK 21+ y Gradle.

```bash
git clone https://github.com/MrIonTv/project-mythus.git
cd project-mythus
./gradlew build
```

---

## Licencia

MIT License — free as in freedom, open as in scripture.
