# Reporte de Errores

## Descripción del Error 1:
- El numero que se adivinaba estaba en el rango entre 1 y 10

# Caso de prueba 1 (donde se encuentra el error): 
- El número a adivinar debe pertenecer al conjunto de los enteros (e.g. 1, 2, 3...)

# Codigo donde se encontraba el error 1:
- let randomNumber = Math.random() * 10;


## Contexto
- Documento: Index.html
- Navegador(es) donde se probo: Google Chrome, Microsoft Edge
- Sistema Operativo: Windows 11

## Pasos de Reproducción del Error 1:
1. Dirigirse al documento index.html dentro del repositorio en Visual Studio Code
2. Verificar (dentro del codigo) que el numero random a adivinar estuviera en el rango. 
3. Este no se encontraba en el rango de 1 - 100 si no, de 1 a 10. 

## Solucion del Error 1:
- let randomNumber = Math.floor(Math.random() * 100) + 1;


## Descripción del Error 2:
- Se podia ingresar cualquier tipo de texto en el Text box de "Ingresa el numero a adivinar:" lo cual demuestra que no se tiene las verificaciones adecuadas para solo recibir numeros enteros.

# Caso de prueba 1 (donde se encuentra el error): 
- El número que ingresará el jugador debe pertenecer al conjunto de los enteros (e.g. 1, 2, 3...), en caso que no ingrese un número entero, debe mostrarse una alerta al usuario y no se debe incrementar un intento de prueba.

# Codigo donde se encontraba el error 2:
- function checkGuess() {

    let userGuess = guessField.value;
    if(guessCount === 1) {
      guesses.textContent = 'Número aleatorio anterior: ';
    }
    guesses.textContent += userGuess + ' ';
    
}
## Contexto
- Documento: Index.html
- Navegador(es) donde se probo: Google Chrome, Microsoft Edge
- Sistema Operativo: Windows 11

## Pasos de Reproducción del Error 2:
1. Dirigirse al documento index.html dentro del repositorio en Visual Studio Code
2. Correr el documento con F5
3. Ingresar el numero a adivinar dentro del Text Box
4. Hacer clic en el botón "Ingresar el numero aleatorio".
5. Observar que acepta cualquier tipo de dato y no verifica que sea numero entero. 

## Solucion para el error 2: 
- 
let userGuess = parseInt(guessField.value); // Parseamos el valor ingresado a un número entero
  if (isNaN(userGuess)) { // Verificamos si no se ingresó un número entero
    alert('Por favor ingresa un número entero.'); // Mostramos una alerta
    return; // Salimos de la función sin incrementar el contador de intentos
  }

  // Verificamos si el número ingresado está fuera del rango 1-100
  if (userGuess < 1 || userGuess > 100) {
    alert('Por favor ingresa un número entre 1 y 100.'); // Mostramos una alerta
    return; // Salimos de la función sin incrementar el contador de intentos
  }

## Descripción del Error 3:
- El mensaje de Incorrecto lo muestra en color negro. 

# Caso de prueba 3 (donde se encuentra el error): 
- Sí el número que ingresó el jugador es mayor al número a adivinar, se debe mostrar el siguiente mensaje en color negro: "Incorrecto! El número es mayor!", en caso que sea menor, se debe mostrar: "Incorrecto! El número es menor!".


# Codigo donde se encontraba el error 3:
- else {
      lastResult.textContent = 'Incorrecto! ';
      lastResult.style.backgroundColor = 'green';
      if(userGuess < randomNumber) {
        lowOrHi.textContent = 'El número es mayor!';
      } else if(userGuess > randomNumber) {
        lowOrHi.textContent = 'El número es menor!';}


## Contexto
- Documento: Index.html
- Navegador(es) donde se probo: Google Chrome, Microsoft Edge
- Sistema Operativo: Windows 11

## Pasos de Reproducción del Error 3:
1. Dirigirse al documento index.html dentro del repositorio en Visual Studio Code
2. Ejecutar el codigo de index.html
3. Ingresar un numero y verificar que no sea el numero que se debe adivinar.
4. El mensaje de Incorrecto sale en color verde, como negro como deberia salir.

## Solucion del Error 3:
- } else {
      lastResult.textContent = '¡Incorrecto!';
      lastResult.style.backgroundColor = 'black';
      if(userGuess < randomNumber) {
        lowOrHi.textContent = 'El número es mayor.';
      } else if(userGuess > randomNumber) {
        lowOrHi.textContent = 'El número es menor.';
      }
    }


## Descripción del Error 4:
- Cuando se completaban 5 intentos, automaticamente salia que se habia ganado el juego. No salia el "Perdiste!" esperado. Ademas solo se tomaban 5 intentos, no los 10 que se esperaban

# Caso de prueba 4 (donde se encuentra el error): 
- Si después de 10 intentos, el usuario no adivina el número, se debe mostrarse el mensaje de color rojo: "!!!Pérdistes!!!"


# Codigo donde se encontraba el error 4:
- En la declaracion de variables : 
  const ATTEMPTS = 5;

- else if(guessCount === ATTEMPS) {
      lastResult.textContent = 'Felicitaciones! adivinaste el número!';
      lastResult.style.backgroundColor = 'red';
      setGameOver();

## Contexto
- Documento: Index.html
- Navegador(es) donde se probo: Google Chrome, Microsoft Edge
- Sistema Operativo: Windows 11

## Pasos de Reproducción del Error 4:
1. Dirigirse al documento index.html dentro del repositorio en Visual Studio Code
2. Ejecutar el codigo de index.html
3. Ingresar un numero, para tratar de adivinar.
4. Ingresar 10 intentos.
5. En el intento 5, salia el mensaje de "Felicidades, adivinaste el numero". A pesar de no haberlo adivinado. Este salia en color rojo. 

## Solucion del Error 4:
- En la declaracion de variables tambien se cambio: 
  const ATTEMPTS = 10;

- } else if(guessCount == ATTEMPTS) {
      lastResult.textContent = '¡Perdiste!';
      lastResult.style.backgroundColor = 'red';
      setGameOver();}



## Descripción del Error 5:
- Cuando se adivina el numero, sale el mensaje de !!!Pérdistes!!! en color negro

# Caso de prueba 5 (donde se encuentra el error): 
- Si el usuario adivina el número antes de los 10 intentos, se debe mostrar el mensaje de color verde: "Felicitaciones! adivinaste el número!".

# Codigo donde se encontraba el error 5:
- if(userGuess === randomNumber) {
      lastResult.textContent = '!!!Pérdistes!!!';
      lastResult.style.backgroundColor = 'black';
      lowOrHi.textContent = '';

    
## Contexto
- Documento: Index.html
- Navegador(es) donde se probo: Google Chrome, Microsoft Edge
- Sistema Operativo: Windows 11

## Pasos de Reproducción del Error 4:
1. Dirigirse al documento index.html dentro del repositorio en Visual Studio Code
2. Ejecutar el codigo de index.html
3. Ingresar un numero, para tratar de adivinar.
4. Adivinar el numero. 
5. Sale el mensaje de "Perdiste!!" en color negro. 

## Solucion del Error 4:
- if(userGuess == randomNumber) {
      lastResult.textContent = '¡Felicitaciones! Adivinaste el número!';
      lastResult.style.backgroundColor = 'green';
      lowOrHi.textContent = '';
      setGameOver(); 
}




¡Gracias por su atención!

