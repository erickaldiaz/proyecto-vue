# proyecto-vue

Two-way data binding es un patrón MVVM (model -> view -> view -> model) donde se enlazan 2 elementos en 2 direcciones (cuando cambia uno cambia el otro)
Sirve para mantener sincronizados los datos con el DOM.
Two-way data binging y en vue pasa de la siguiente manera:
El estado comunica a la vista qué es lo que va a modificar y la vista (donde el usuario interactúa con la app) responde con los cambios provocados por el usuario para que el estado vuelva a empezar con el proceso.

![image](https://user-images.githubusercontent.com/30804734/112576983-33677980-8dd2-11eb-9505-e8611d725779.png)

Las directivas es la herramienta que nos ofrece Vue para poder manipular el DOM y para poder manipularlo de forma declarativa.
Es decir, que podemos utilizar diferentes tags dentro de nuestros elementos HTML.

Las directivas de Vue siempre se escriben con v corta, guión y el nombre de la directiva.0
Ejemplo: v-bind:src=“img” v-bind:alt="name"
Así podemos definir valores dinámicos para estos atributos.

![image](https://user-images.githubusercontent.com/30804734/112584531-c73b4480-8dd6-11eb-80fa-cd24bc73cebf.png)

Control de flujo con directivas

La principal diferencia entre v-if y v-show es que v-if renderiza el elemento en el DOM solo si se cumple la expresión y v-show renderiza todos los elementos en el DOM y luego utiliza la propiedad display de CSS para ocultarlo si no cumple con la expresión.
v-show se utiliza preferentemente si el elemento cambia frecuentemente y v-if cuando no cambia a lo largo del tiempo

![image](https://user-images.githubusercontent.com/30804734/112585877-724cfd80-8dd9-11eb-925e-6093dc9bb445.png)

Renderizado de listas

Se utiliza la directiva v-for para recorrer el array.
v-for = “p in prices”
.
Al utilizar esta directiva se recomienda el uso de key, ya que permite identificar de manera unívoca a cada elemento. Esto permite que si la lista se reordene, modifique o actualice la lista pueda seguir identificando cual es el elemento.
.
Podemos llamar al indice del elemento de la lista:
v-for="(p,i) in prices"

v-for = " (p, i) …"
p hace referencia al elemento en sí
i al índice del elemento.

![image](https://user-images.githubusercontent.com/30804734/112587595-a1b13980-8ddc-11eb-9e92-236af75afeba.png)



Methods
Es una propiedad de la instancia de Vue. Es un objeto donde se pueden definir funciones que pueden ser disparados por acciones en la vista.
Para acceder a propiedades de otro scope se utiliza la keyword this seguido de un punto y el nombre de la propiedad.
![image](https://user-images.githubusercontent.com/30804734/112662291-46ac3080-8e36-11eb-8f01-010883dd119b.png)

Y se agrega la directiva v-on ante determinado evento en el HTML que permite disparar el método.
![image](https://user-images.githubusercontent.com/30804734/112662475-8115cd80-8e36-11eb-87fc-3980bcf1fc1d.png)


Otra directiva que se puede utilizar en v-on es mouseover:

![image](https://user-images.githubusercontent.com/30804734/112667855-8aa23400-8e3c-11eb-8276-ea9e571aa4e9.png)


Se puede modificar el atributo class de una etiqueta usando la directiva v-bind: usando operador ternario( changePercent > 0 ? 'green' : 'red' ESTA OPERACIÓN TERNARIA ES LO MISMO QUE if changepercent > 0 { show: 'green' } else { show: 'red' } ) o validando con objetos.
El uso de v-bind:class es completamente combinable con class, por lo tanto se puede tener un v-bind:class junto con una clase y no genera error.

![image](https://user-images.githubusercontent.com/30804734/112672124-dc998880-8e41-11eb-99a3-80ed2f58f992.png)


También se pueden aplicar style directamente a un elemento del DOM mediante un objeto:
![image](https://user-images.githubusercontent.com/30804734/112709010-93beef80-8e94-11eb-8450-97011e55242d.png)

en app.js
![image](https://user-images.githubusercontent.com/30804734/112709027-a9ccb000-8e94-11eb-92f0-7c404bbfad4b.png)


Propiedades computadas (Computed) = propiedades que se calculan en tiempo real en base a los valores de otras propiedades.
![image](https://user-images.githubusercontent.com/30804734/112711990-4ac66580-8eab-11eb-8440-a925530f9c8d.png)


Watcher = Funciones que por medio de un cambio de la observación de una variable se puede disparar la función. Es un disparador de código.
![image](https://user-images.githubusercontent.com/30804734/112711976-31251e00-8eab-11eb-84b0-ad3ef233b256.png)

#Two-Way Data Binding:

La directiva v-model permite linkear las cosas que puede escribir el usuario mediante un input con las propiedades que tenemos definidas en data. Es lo que permite que cada vez que se cambia la vista a través de interacciones con el usuario se actualice el código y cada vez que se actualice el código también se actualice la vista.
en index.html
![image](https://user-images.githubusercontent.com/30804734/112712531-00df7e80-8eaf-11eb-9597-bf6c2dab7cba.png)

En app.js
Dentro de data se agrega la propiedad value y se inicializa en 0. Y dentro de computed porque se opera con dos propiedades de data se agrega esta función para que retorne el valor de la operación.
![image](https://user-images.githubusercontent.com/30804734/112712542-12288b00-8eaf-11eb-8965-f89730abd075.png)

SISTEMA DE COMPONENTES

Los componentes son la segunda funcionalidad importante que tiene Vue. Se basan en las especificaciones de web components APIs. Permiten modularizar mi aplicación en diferentes pedazos de htm, javascript y Css para tener un código más legible y semántico. Es decir, cada componente puede ser utilizado a lo largo del proyecto, tiene todo lo que necesita para existir, tiene su lógica, tiene diseño y tiene estructura.

Cuando se trabaja con Html y el DOM siempre tenemos una estructura de árbol, es decir, una estructura jerárquica DOM. Tenemos un componente principal (en este caso, el recuadro azul en la imagen abajo) y luego tenemos componentes hijos que representan contenedores con diferente tipo de contenido. Además, podemos tener otros componentes hijos, es decir, cada uno también tiene sus propios elementos Html.

Estructura que manejamos con el dom
![image](https://user-images.githubusercontent.com/30804734/112712808-6a13c180-8eb0-11eb-87fd-d0ef495d4fcb.png)

entonces podemos decir que la estructura al ser de árbol, siempre tiene un componente principal y componentes hijos que salen de ese componente principal. Este componente principal estaba representado por lo que conocemos como el componente root, o nuestra aplicación (App, en este caso) y luego tenemos los componentes hijos, como puede ser un header , un footer y después diferente tipo de contenido que podemos tener a lo largo nuestra estructura. La idea de los componentes es llevar toda nuestra lógica a pedazos de Html reutilizables que luego vamos a escribir de manera muy sencilla y semántica dentro de nuestro elemento o dentro de nuestro componente principal.

Por ejemplo, podríamos pensar un componente que tenga un header de Html, que también tenga algo así como un componente que se llame login . De igual modo otro componente que podría ser Custom y luego tener un footer. De esta forma combinamos los elementos de Html5 con nuestros propios componentes para conseguir un código semántico y además tenemos la ventaja de que dentro de otra página o dentro de otro componente, también podemos utilizar los componentes que creamos, por ejemplo, el componente Custom o el componente footer que es nativo de Html

![image](https://user-images.githubusercontent.com/30804734/112712859-c971d180-8eb0-11eb-8db4-5cafa37e0b73.png)


Component
para crear un componente se utiliza la propiedad component de Vue, este tiene el metodo template donde va el “html” de nuestro componente

🐪 camelCase
🧮 PascalCase
🐍 snake_case
🍢 kebab-case

Props

En props definimos las propiedades que el componente padre le va a enviar al hijo. Los props se utilizan igual que las propiedades de data, se utilizan a través de this. El componente hijo no puede escribir o modificar los props que le mande el padre.
El nombre del componente se escribe en Pascal Case, donde cada palabra inicia con la primera letra en mayúscula. Al momento de llamar al componente en el HTML, Vue parsea el nombre a Kebab Case, una nomenclatura con guiones lo cual permite mantener una consistencia con los tags HTML.
Se recomienda mantener la consistencia entre los lenguajes, utilizar Pascal Case dentro de JavaScript: CoinDetail ; y Kebab Case dentro de HTML: coin-detail.
Para pasarle las propiedades al componente se hace desde el HTML usando la directiva v-bind: v-bind:change-percent = “changePercent”. Aquí también aplica lo del Kebab Case.
Los componentes de Vue necesitan tener un componente padre único que encierre a todos los demás.
Cuando las propiedades tienen un elemento central común es más cómodo trabajarlas mediantes un objeto, así evitamos tener que estar pasando tantos props.

![image](https://user-images.githubusercontent.com/30804734/112759776-ed293a80-8fca-11eb-9824-7454622e12cf.png)

COMUNICACIÓN ENTRE COMPONENTES: EVENTOS

¿Qué debemos hacer cuando un componente hijo necesita enviar información a un componente padre? Lo que debemos hacer es enviar eventos. Las propiedades del componente padre nunca deben ser actualizadas por el componente hijo. En caso de que haya que modificar una de estas propiedades, el componente hijo tiene que notificar al padre y esta notificación se hace a través de eventos. Se puede decir entonces que la comunicación de padre a hijo es con propiedades y de hijos a padres es con eventos. De esta manera mantenemos la consistencia en Vue.js.

Recordemos que usamos el v-bind para modificar en tiempo real o tener un atributo dinámico en cuanto a las propiedades y vamos a usar la emisión de eventos con la directiva v-on para que el componente hijo pueda enviar información al componente padre.

Tomando el código de la clase precedente, lo que vamos a hacer ahora es modificar la variable color del componente padre usando el componente hijo. El componente hijo debe emitir un evento para avisarle al componente padre.

Vamos a hacerlo con la función this.$emit(‘change-color’) inserta en la función toggleShowPrices() que está en methods del componente hijo.

![image](https://user-images.githubusercontent.com/30804734/112760881-f0bec080-8fce-11eb-90ab-12e8464abf17.png)

Luego, en el Html , en <coin-detai> insertamos la directiva v-on: change-color=”updateColor ” (Significa: escuchar al evento change-color)
  
  ![image](https://user-images.githubusercontent.com/30804734/112760965-42ffe180-8fcf-11eb-97eb-2f32d168a319.png)
  
  Ahora, en el componente principal (el padre) se define, en este ejemplo, el comportamiento de change-color
  Al momento de emitir un evento también podemos emitir un valor que vaya acompañando ese evento. En el argumento de la función this.$emit(‘change-color’) colocaremos el color que queremos, asi:
  
  ![image](https://user-images.githubusercontent.com/30804734/112760988-5d39bf80-8fcf-11eb-9bb9-5ba921aa36e0.png)
  
  Slots
  En los componentes cuando ocupamos recibir contenido en lugar de recibir propiedades, podemos utilizar Slots que es una API de distribución de contenido que permite que un componente padre le inyecte HTML a un componente hijo.
Para utilizar varios Slots, se debe colocar un nombre a cada slot para identificarlos:<slot name="text"></slot>
Y para llamar al Slot en el HTML se debe encerrar el Slot dentro del tag template que es un tag de VueJS, que permite renderizar contenido sin la necesidad de utilizar un tag, el tag template en la renderización final es eliminado:


![image](https://user-images.githubusercontent.com/30804734/112764071-692c7e00-8fdd-11eb-8dfa-fbbd2a3ac6c5.png)






