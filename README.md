## **Desafío: Mejora de la tasa de renovación de las suscripciones**

Le han pedido que agregue una característica al software de su empresa. La característica está pensada para mejorar la tasa de renovación de las suscripciones al software. Su tarea consiste en mostrar un mensaje de renovación cuando un usuario inicia sesión en el sistema de software y se notifica que su suscripción finaliza pronto. Para cumplir los requisitos, necesitará agregar un par de instrucciones de decisión para agregar lógica de rama a la aplicación.

## **Preparación del entorno de creación de código**

1. Asegúrese de que tiene un archivo Program.cs vacío abierto en Visual Studio Code.
    
    Si es necesario, abra Visual Studio Code y, luego, lleve a cabo los pasos siguientes para preparar un archivo Program.cs en el editor:
    
    1. En el menú **Archivo**, seleccione **Abrir carpeta**.
    2. Use el cuadro de diálogo "Abrir carpeta" para ir a la carpeta **CsharpProjects**.
    3. En el panel EXPLORADOR de Visual Studio Code, seleccione **Program.cs**.
    4. En el menú **Selección** de Visual Studio Code, elija **Seleccionar todo** y presione la tecla Supr.
2. Para crear el código inicial de este desafío, escriba el código siguiente:
    
    ```csharp
    Random random = new Random();
    int daysUntilExpiration = random.Next(12);
    int discountPercentage = 0;
    
    // Your code goes here
    ```
    
    Observe que este código generará un número aleatorio con un valor de 0 a 11. El número aleatorio se asigna a una variable de entero denominada `daysUntilExpiration` . Tiene otra variable entera denominada       `discountPercentage` que se inicializa en `0`.
    
    <aside>
    💡 **Importante**
    En este desafío, solo puede quitar el comentario de código. En otras palabras, puede quitar la línea de código que empieza por `//`, pero no puede quitar ningún otro código. Además, debe usar todas las variables en la solución.
    
    </aside>
    

## **Revise las reglas de negocio para este desafío.**

1. Regla 1: El código solo debe mostrar un mensaje.
    
    El mensaje que el código muestra dependerá de las otras cinco reglas. En el caso de las reglas 2 a 6, las reglas con numeración más alta tienen prioridad sobre las reglas con numeración más baja.
    
2. Regla 2: Si la suscripción del usuario expira en 10 días o menos, muestre el mensaje:
    
    ```
    Your subscription will expire soon. Renew now!
    ```
    
3. Regla 3: Si la suscripción del usuario expira en 5 días o menos, muestre los mensajes:
    
    ```
    Your subscription expires in _ days.
    Renew now and save 10%!
    ```
    
    <aside>
    💡 **Nota**
    Asegúrese de reemplazar el carácter  `_` mostrado en el mensaje anterior por el valor almacenado en la variable  `daysUntilExpiration` al construir la salida del mensaje.
    
    </aside>
    
4. Regla 4: Si la suscripción del usuario expira en un día, muestre los mensajes:
    
    ```
    Your subscription expires within a day!
    Renew now and save 20%!
    ```
    
5. Regla 5: Si la suscripción del usuario ha expirado, muestre el mensaje:
    
    ```
    Your subscription has expired.
    ```
    
6. Regla 6: Si la suscripción del usuario no expira en 10 días o menos, no muestre ningún mensaje.

## **Implementación del código de la solución mediante instrucciones if**

La solución debe usar las instrucciones `if` y `if-else` independientes para implementar las reglas de negocio. La instrucción `if-else` puede incluir varias partes `else if`.

1. Cree una instrucción `if-else` que muestre un mensaje sobre cuándo expirará la suscripción.
    
    > **Sugerencia**
    Use `else if` para asegurarse de que cada regla de extensión tenga en cuenta.
    > 
2. Cree una instrucción `if` independiente que muestre una oferta de descuento.
    
    Las reglas de negocios indican cuándo se debe ofrecer un descuento.
    

Tanto si tiene dificultades y necesita echar un vistazo a la solución como si finaliza el ejercicio correctamente, continúe para ver una solución a este desafío.

SOLUCIÓN del creador:

```
Random random = new Random();
int daysUntilExpiration = random.Next(12);
int discountPercentage = 0;

if (daysUntilExpiration == 0)
{
    Console.WriteLine("Your subscription has expired.");
}
else if (daysUntilExpiration == 1)
{
    Console.WriteLine("Your subscription expires within a day!");
    discountPercentage = 20;
}
else if (daysUntilExpiration <= 5)
{
    Console.WriteLine($"Your subscription expires in {daysUntilExpiration} days.");
    discountPercentage = 10;
}
else if (daysUntilExpiration <= 10)
{
    Console.WriteLine("Your subscription will expire soon. Renew now!");
}

if (discountPercentage > 0)
{
    Console.WriteLine($"Renew now and save {discountPercentage}%.");
}
```