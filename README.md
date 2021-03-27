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


Compponent
para crear un componente se utiliza la propiedad component de Vue, la cual tiene casi los mismos metodos que la instancia de Vue donde veniamos haciendo todo, nada mas que este tiene el metodo template donde va a ir el “html” de nuestro componente 😄

