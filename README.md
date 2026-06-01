# robo-rescate
# 🚀 Space Collector Engine

## 🎮 Temática del juego

**Space Collector** es un motor de videojuego 2D por consola donde el jugador controla una nave espacial que debe recoger cristales de energía mientras evita enemigos alienígenas.

El objetivo es simular la lógica interna de un videojuego (sin interfaz gráfica) usando Java y programación orientada a objetos.

---

## 🧠 Arquitectura del software

El sistema está compuesto por 5 clases principales:

- **Main** → Simula el juego y el game loop.
- **MotorJuego** → Controla el estado del juego, entidades y lógica principal.
- **EntidadVideojuego** → Representa jugador, enemigos y objetos.
- **GestorEntradas** → Simula los controles del jugador.
- **SistemaPuntuacion** → Gestiona puntos, eliminaciones y logros.

---

## 📊 Diagrama de clases UML

```mermaid
classDiagram

class Main {
    +main(String[] args)
}

class MotorJuego {
    -String estado
    -List~EntidadVideojuego~ entidades
    -SistemaPuntuacion puntuacion
    +iniciarPartida()
    +pausar()
    +reanudar()
    +gameOver()
    +actualizar()
    +agregarEntidad()
    +detectarColisiones()
}

class EntidadVideojuego {
    -String nombre
    -String tipo
    -int x
    -int y
    -int vida
    +mover(int dx, int dy)
}

class SistemaPuntuacion {
    -int puntos
    -int enemigosEliminados
    -List~String~ logros
    +sumarPuntos(int valor)
    +registrarEliminacion()
}

Main --> MotorJuego
MotorJuego --> EntidadVideojuego
MotorJuego --> SistemaPuntuacion
| Campo                   | Descripción                                                                                                                                  |
| ----------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| **Nombre**              | CU-01 Iniciar Partida                                                                                                                        |
| **Objetivo**            | Iniciar una nueva partida del motor de juego                                                                                                 |
| **Actor Principal**     | Jugador                                                                                                                                      |
| **Precondiciones**      | El juego debe estar en estado MENU                                                                                                           |
| **Flujo Principal**     | 1. El jugador inicia el juego.<br>2. El motor cambia a estado JUGANDO.<br>3. Se crean las entidades del juego.<br>4. Se inicia el game loop. |
| **Flujos Alternativos** | Si el juego ya está en partida, no se reinicia.                                                                                              |
| **Postcondiciones**     | El estado del juego pasa a JUGANDO                                                                                                           |
| **Reglas de Negocio**   | No se puede iniciar una partida si ya hay una activa                                                                                         |
| Campo                   | Descripción                                                                                                             |
| ----------------------- | ----------------------------------------------------------------------------------------------------------------------- |
| **Nombre**              | CU-02 Recoger Cristal                                                                                                   |
| **Objetivo**            | Aumentar la puntuación del jugador al recoger un objeto                                                                 |
| **Actor Principal**     | Jugador                                                                                                                 |
| **Precondiciones**      | El jugador debe estar en estado JUGANDO                                                                                 |
| **Flujo Principal**     | 1. El jugador se mueve.<br>2. Colisiona con un cristal.<br>3. El sistema detecta la colisión.<br>4. Se suma puntuación. |
| **Flujos Alternativos** | Si no hay colisión, no ocurre nada                                                                                      |
| **Postcondiciones**     | Aumenta la puntuación del jugador                                                                                       |
| **Reglas de Negocio**   | Cada cristal vale 100 puntos                                                                                            |
🤖 Bitácora del uso de Inteligencia Artificial
Herramienta utilizada
ChatGPT (OpenAI)
Rol asignado

Asistente para:

Diseño del motor del videojuego
Generación de código Java
Creación de diagramas UML
Documentación técnica
Añade colisiones, sistema de puntuación y comportamiento de enemigos en un juego 2D por consola en Java.
⚠️ Error detectado en la IA

Inicialmente la IA generó demasiadas clases (Jugador, Enemigo, Cristal, EstadoJuego), lo que incumplía la restricción del enunciado.

Se corrigió unificando todo en una sola clase EntidadVideojuego con un atributo tipo.

🧩 Reflexión crítica

El uso de IA acelera el diseño del software y la generación de estructuras complejas como UML o lógica de juego.

Sin embargo, puede generar:

Sobreingeniería
Exceso de clases
Diseños no ajustados a restricciones

Por ello es necesaria la supervisión humana para asegurar que el resultado cumpla los requisitos académicos.

🏁 Conclusión

Este proyecto implementa un motor básico de videojuego 2D en consola usando Java, aplicando programación orientada a objetos, control de estados, colisiones, puntuación y comportamiento de enemigos.
