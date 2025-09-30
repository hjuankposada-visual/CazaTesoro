# CazaTesoro
Versión 1 del juego caza tesoro.

using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Bienvenido a la Gran Caza del Tesoro");
        Console.WriteLine("Tu misión: encontrar el cofre escondido entre el 0 y un número que tú elijas.");

        // 1️⃣ Solicitar el número máximo al usuario
        Console.Write("Ingresa el número máximo del mapa del tesoro: ");
        if (!int.TryParse(Console.ReadLine(), out int limite))
        {
            Console.WriteLine("Eso no es un número válido. ¡Fin de la aventura!");
            return;
        }

        // 2️⃣ Validar si el número máximo es mayor que cero
        if (limite <= 0)
        {
            Console.WriteLine("El mapa no puede tener un límite menor o igual a cero. ¡No se puede jugar!");
            return;
        }

        // 3️⃣ Calcular un número aleatorio entre 0 y el límite
        Random random = new Random();
        int tesoro = random.Next(0, limite + 1); // Incluye el límite

        // 4️⃣ Pedirle al usuario su intento
        Console.Write($"Adivina dónde está escondido el tesoro (entre 0 y {limite}): ");
        if (!int.TryParse(Console.ReadLine(), out int intento))
        {
            Console.WriteLine("Entrada no válida. La expedición termina aquí.");
            return;
        }

        // 5️⃣ Mostrar si ganó o perdió
        if (intento == tesoro)
        {
            Console.WriteLine("¡Felicidades, aventurero! ¡Has encontrado el tesoro escondido!");
        }
        else
        {
            Console.WriteLine($"Lo siento... El tesoro estaba en el {tesoro}. Intenta nuevamente.");
        }

        Console.WriteLine("Fin de la aventura. ¡Gracias por jugar!");
    }
}
