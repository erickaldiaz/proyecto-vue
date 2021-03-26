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
