## 2.5 Strategic-Level Domain-Driven Design

### 2.5.1 Event Storming

Event Storming es una herramienta que nos permite descubrir el comportamiento de un negocio, recopilando eventos importantes del
negocio, los actores principales, servicios de terceros y otros. Para la implementación de esta sección se realizaron entrevistas
correspondientes a los segmentos objetivos, de esta manera pudimos identificar los eventos principales y desarrollar un entendimiento
común

Aquí mostramos los pasos respectivos para la elaboración correcta del Event Storming realizada en la herramienta Miro:

#### Paso 1: Unstructured Exploration
En esta sección se realizó una lluvia de ideas de los eventos del dominio relacionados con el dominio empresarial que se está
explorando. Nos permitió identificar los eventos clave y las interacciones entre ellos.


<img src="images/Event Storming-1.jpg">

#### Paso 2: Timelines

En esta sección, los eventos identificados previamente, son agrupados en subgrupos lo cual tiene como líder al evento principal (es
quien encapsula la funcionalidad principal del grupo). Estos eventos comienzan con el flujo que describe el escenario empresarial
exitoso (Happy path) y también escenarios alternativos.

<img src="images/Event Storming-2.jpg"/>

#### Paso 3: Paint Points

Durante esta fase, identificamos puntos problemáticos o (Paint Points) que son áreas donde los usuarios pueden tener dificultades al
momento de realizar una respectiva funcionalidad en la aplicación. Estos puntos son importantes para mejorar la experiencia de usuario
e implementar una aplicación eficiente

<img src="images/Event Storming-3.jpg"/>

#### Paso 4 : Pivotal Points

En esta fase, nos enfocamos en identificar los puntos cruciales dentro del flujo del negocio, los cuales tienen un impacto significativo en
la operatividad del sistema o el comportamiento del usuario. Estos puntos nos ayudan a priorizar qué áreas deben ser optimizadas o
revisadas con mayor detalle, ya que pueden afectar el éxito de los procesos empresariales críticos.

<img src="images/Event Storming-4.jpg">

#### Paso 5: Commands

Los comandos representan acciones que los actores del sistema pueden ejecutar. Durante este paso, mapeamos qué acciones
desencadenan los eventos clave dentro del sistema y qué actores son responsables de ejecutarlas. Esto nos ayuda a estructurar la
lógica de negocio alrededor de acciones claras y específicas, facilitando la implementación de las reglas del negocio

<img src="images/Event Storming-5.jpg">

#### Paso 6: Policies

En este paso, se identifican las políticas, que son reglas de negocio o condiciones que deben cumplirse para que un comando pueda ser
ejecutado o un evento pueda suceder. Las políticas son esenciales para definir las restricciones del sistema y asegurar que el flujo de
eventos sea coherente con las reglas del negocio.

<img src="images/Event Storming-6.jpg" />

#### Paso 7: Read Models
Los Read Models son vistas del estado del sistema, generalmente optimizadas para la consulta por parte de los usuarios o procesos.
Durante este paso, definimos qué información necesita ser accesible en ciertos momentos y cómo debería ser presentada, asegurando
que los actores puedan visualizar el estado del sistema de manera eficiente.

<img src="images/Event Storming-7.jpg">

#### Paso 8:  External Systems

En esta fase, identificamos los sistemas externos que interactúan con nuestro dominio. Aquí mapeamos las conexiones con servicios de
terceros o sistemas independientes que influyen en los eventos del negocio. Es crucial entender cómo estos sistemas externos afectan
los flujos y asegurar que las integraciones sean correctas.

<img src="images/Event Storming-8.jpg">

#### Paso 9: Aggregates

En este último paso, agrupamos los eventos y comandos que pertenecen a un agregado específico para garantizar que todas las
operaciones dentro de un contexto estén alineadas y mantengan la consistencia del sistema.

<img src="images/Event Storming-9.jpg">


### 2.5.1.1. Candidate Context Discovery

Nuestro equipo decidió usar la técnica “start-with-simple” ya que empezamos a observar que esta técnica se enfoca en identificar partes
del sistema que claramente pertenecen juntas desde el punto de vista funcional, de usuario o de infraestructura. Ideal para sistemas
bien entendidos

Hemos identificado 6 Bounded Context.

- IAM

<img src="images/IAM.jpg" />

- Farm Management

<img src="images/Farm-Management.jpg" />

- Bovinue Management

<img src="images/Bovinue-Management.jpg" />

- Bovinue Configuration

<img src="images/Bovinue-Config.jpg" />

- Farm Configuration

<img src="images/Farm-Config.jpg" />

- Shared

<img src="images/Shared.jpg" />

### 2.5.1.2. Domain Message Flows Modeling

En esta sección, se describe el proceso utilizado para visualizar la interacción entre los diferentes bounded contexts que conforman el
sistema. El objetivo principal es entender cómo estos contextos colaboran para resolver los casos de uso del negocio y satisfacer las
necesidades de los usuarios. Para lograr esto, se aplicó la técnica de Domain Storytelling, que facilita la representación gráfica de los
flujos de mensajes entre actores, contextos y sistemas, permitiendo identificar claramente las responsabilidades y los puntos de
comunicación entre cada componente del dominio

- IAM -> Shared

<img src="images/registrarion-work.jpg" >

- Farm Management -> Bovinue Management -> Bovinue Configuration

<img src="images/bovinos-modification.jpg" >

- Farm Configuration -> Shared

<img src="images/farmconfig-shared.jpg">
