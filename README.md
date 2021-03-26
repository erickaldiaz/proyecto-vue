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



