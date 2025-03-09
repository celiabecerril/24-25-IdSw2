# Revisión de Código y Mejora de Buenas Prácticas

Este documento contiene una serie de observaciones sobre el código en el repositorio, identificando problemas relacionados con nombres no descriptivos, inconsistencias en los nombres, problemas de sintaxis, repetición de código y falta de encapsulación. A continuación, se detallan los problemas encontrados junto con sugerencias de mejora.

## 1. Nombres No Descriptivos o Ambiguos

- [`Parcial.java#L9`](https://github.com/celiabecerril/23-24-prg2-ep/blame/445ddf27e1ca6e7870647bf9760e6f23f7a4daf0/src/Parcial.java#L9)
  - **teacher2** no es un nombre descriptivo. Un mejor nombre podría ser `examSupervisor`.
- [`Parcial.java#L6`](https://github.com/celiabecerril/23-24-prg2-ep/blame/445ddf27e1ca6e7870647bf9760e6f23f7a4daf0/src/Parcial.java#L6)
  - **teacher1** tampoco es descriptivo. Se recomienda cambiarlo a `mainTeacher`.

## 2. Uso de Nombres Inconsistentes

- [`Parcial.java#L40`](https://github.com/celiabecerril/23-24-prg2-ep/blame/445ddf27e1ca6e7870647bf9760e6f23f7a4daf0/src/Parcial.java#L40)
  - Error tipográfico en el nombre del método `deteleSubject`, debería ser `deleteSubject`.
- [`Parcial.java#L75`](https://github.com/celiabecerril/23-24-prg2-ep/blame/445ddf27e1ca6e7870647bf9760e6f23f7a4daf0/src/Parcial.java#L75)
  - `Boolean` debería ser `boolean`.
  - `isNie` no es claro, se recomienda cambiarlo a `hasValidNieFormat`.
- [`Parcial.java#L99C18`](https://github.com/celiabecerril/23-24-prg2-ep/blame/445ddf27e1ca6e7870647bf9760e6f23f7a4daf0/src/Parcial.java#L99C18-L99C18)
  - `editQuestion` no refleja su funcionalidad. Si modifica el nombre de la pregunta, debería llamarse `setQuestionText`.

## 3. Problemas de Sintaxis

- [`Restaurante#L18`](https://github.com/celiabecerril/23-24-prg2/blob/ba7bfd13af67c130d097c983f2d370d6ae5e9bd0/entregas/BecerrilCelia/Reto-003/Restaurante#L18)
  - Faltan `()` para indicar que son métodos.

## 4. Métodos Repetitivos

- [`Restaurante#L28`](https://github.com/celiabecerril/23-24-prg2/blob/ba7bfd13af67c130d097c983f2d370d6ae5e9bd0/entregas/BecerrilCelia/Reto-003/Restaurante#L28) 
- [`Restaurante#L40`](https://github.com/celiabecerril/23-24-prg2/blob/ba7bfd13af67c130d097c983f2d370d6ae5e9bd0/entregas/BecerrilCelia/Reto-003/Restaurante#L40)
  - Se recomienda renombrar y hacer métodos de acceso como `getCliente()`.

## 5. Código No DRY (Don't Repeat Yourself)

- [`Player.java#L12`](https://github.com/celiabecerril/23-24-prg2-PPT/blob/3c634214be9f26a52c33681d229140c2c7f69251/entregas/BecerrilRianoCelia/PPT/Player.java#L12)
  - El uso de `switch` para asignar `choice` repite datos que podrían estar en una lista predefinida.
  - Se recomienda reemplazarlo con:
    ```java
    String[] choices = {"Piedra", "Papel", "Tijeras"};
    choice = choices[random.nextInt(3)];
    ```

## 6. Falta de Encapsulación

- [`Game.java#L11`](https://github.com/celiabecerril/23-24-prg2-PPT/blob/3c634214be9f26a52c33681d229140c2c7f69251/entregas/BecerrilRianoCelia/PPT/Game.java#L11)
  - Se recomienda dividir el método `play()` en submétodos como `playRound()`.
