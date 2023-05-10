Claves de testeo
_________________



1.  La Ortografía es importante para los clientes, se encontraron faltas ortográficas en 
    las instrucciones del programa
 
Se corrigieron las palabras:

    aleatorío -> aleatorio

2.  También es importante ser claros, concisos y utilizar correctamente el lenguaje.
        
        "Hemos seleccionado un número aleatorio entre 1 a 100."
        "Hemos seleccionado un número aleatorio entre 1 y 100."

        "Trata de adivinar el número, en un total de 10 turnos o menos."
        "Trata de adivinar el número, tienes como máximo 10 intentos."

        "No te preocupes, te diremos sí el número es más alto o más bajo"
        "No te preocupes, te diremos si el número es mayor o menor al ingresado."
        
3. Errores de funcionamiento.

    Se encontró un error en el funcionamiento del programa al presionar el botón.

        No se está haciendo referencia correctamente a la función.

            guessSubmit.addeventListener('click', checkGuess); 
        
        Se corrige colocándolo de la siguiente manera:

            guessSubmit.addEventListener('click', checkGuess); 

        No se está haciendo referencia correctamente a la función.

            resetButton.addeventListener('click', resetGame); 
        
        Se corrige colocándolo de la siguiente manera:

            resetButton.addEventListener('click', resetGame);

        Hace falta hacer referencia correctamente a la clase:
            
            const lowOrHi = document.querySelector('lowOrHi');

        Para ello se requiere de un punto (.) antes del nombre de la clase.
            
            const lowOrHi = document.querySelector('.lowOrHi');

4. No se están realizando correctamente las validaciones.

    if (userGuess === randomNumber) {
        lastResult.textContent = '!!!Pérdistes!!!';
        lastResult.style.backgroundColor = 'black';
        lowOrHi.textContent = '';
        setGameOver();
    }
    En la consecuencia debería ir lo siguiente:

    if (userGuess === randomNumber) {
        lastResult.textContent = 'Felicitaciones! adivinaste el número!';
        lastResult.style.backgroundColor = 'red';
        //Ocultar mensaje de mayor o menor
        lowOrHi.textContent = '';
        setGameOver();
    }

    Cuando se llegan a los 10 intentos.
    
    else if (guessCount === ATTEMPS) {
        lastResult.textContent = 'Felicitaciones! adivinaste el número!';
        lastResult.style.backgroundColor = 'red';
        //Ocultar mensaje de mayor o menor
        lowOrHi.textContent = '';
        setGameOver();
    }

    Debería ir lo siguiente:

    else if (guessCount === ATTEMPS) {
        lastResult.textContent = '!!!Pérdistes!!!';
        lastResult.style.backgroundColor = 'black';
        lowOrHi.textContent = '';
        setGameOver();
    }


5.  Se dijo que eran 10 intentos.
        Se corrige la variable 
            const ATTEMPS = 10;

    

5.  Se está calculando mal el número aleatorio y no se generan de 1 a 100.

        Se están generando decimales y solamente entre 0 y 10
        let randomNumber = Math.random() * 10;

        Se corrige haciendo una aproximación para que se generen únicamente números enteros.

            let randomNumber = Math.floor(Math.random() * 99 + 1);

6.  Verificación incorrecta.
        if (userGuess === randomNumber)

        El triple "===" sirve para comparar contenido y tipo de dato.

        Se corrige quitando uno y utilizando el doble "=="
        
        if (userGuess == randomNumber)


En general esos fueron los errores que encontré. Puede que existan más ya que ningún sistema es perfecto pero para eso estamos los programadores para poder perfeccionar nuestros sistemas. Con lo resuelto, el usuario tendrá una buena experiencia en el sistema.
    

        
    