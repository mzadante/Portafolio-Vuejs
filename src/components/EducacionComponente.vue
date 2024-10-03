<script setup>
import { ref } from 'vue';
const fechaColor = ref([]);
/*Esta es otra forma de utilizar el arreglo, con el metodo value*/
fechaColor.value = [
  {color: '#41516c'},
  {color: '#FBCA3E'},
  {color: '#E24A68'},
  {color: '#1B5F8C'},
  {color: '#4CADAD'}
];
/*Esta es la forma de utilizar el arreglo, sin el metodo value*/
const educacion = ref([
  {fecha: '2024', title: 'Técnicatura Universitaria en Programacion', descripcion: 'Incumbencias Profesionales: Operación y programación de computadoras, desarrollo de programas en distintos lenguajes, análisis y control de sistemas informáticos.', enlace:'https://www.youtube.com/'},
  {fecha: '2023', title: 'Desarrollador Full Stack', descripcion: 'Trabajé en XYZ Tech, donde diseñé y desarrollé aplicaciones web completas utilizando tecnologías como Node.js, React y MongoDB.', enlace:'http:www.direccion.com'},
  {fecha: '2022', title: 'Internship en Desarrollo Web', descripcion: 'Realicé una pasantía en ABC Solutions, contribuyendo en la creación de interfaces de usuario y optimización de sitios web.', enlace:'http:www.direccion.com'},
  {fecha: '2021', title: 'Proyecto Personal - Aplicación de Gestión de Tareas', descripcion: 'Desarrollé una aplicación para la gestión de tareas diarias usando HTML, CSS y JavaScript, implementando funcionalidades como listas de tareas y recordatorios.', enlace:'http:www.direccion.com'},
  {fecha: '2020', title: 'Curso de Introducción a la Programación', descripcion: 'Completé un curso en línea sobre fundamentos de programación, donde aprendí lenguajes como Python y Java.', enlace:'http:www.direccion.com'}
]);
</script>

<template>
    <ul>
        <li v-for="(item, index) in educacion" :key="index" :style="{ '--fecha-color': fechaColor[index].color}">
        <div class="fecha">{{ item.fecha }}</div>
        <h3 class="title">{{ item.title }}</h3>
        <div class="descripcion">{{ item.descripcion }}</div>
        <!--Aqui vemos con el uso de b-vind (:) que bindeamos el atributo href de html con el item.enlace-->
        <a class="enlace" :href="item.enlace" target="_blank">Saber más</a>
    </li>
    </ul>
</template>

<style scoped>
/* Estilos generales */
@import url("https://fonts.googleapis.com/css2?family=Poppins:wght@300;500;700&display=swap");
/* Reseteo de estilos básicos para todos los elementos y pseudo-elementos */
*,
*::before,
*::after {
  margin: 0; /* Elimina el margen predeterminado */
  padding: 0; /* Elimina el padding predeterminado */
  box-sizing: border-box; /* Incluye el padding y el borde en el tamaño total del elemento */
}

/* Estilo para el cuerpo de la página */
body {
  --color: rgba(30, 30, 30); /* Variable para el color de texto */
  --bgColor: rgba(245, 245, 245); /* Variable para el color de fondo */
  min-height: 100vh; /* Asegura que el cuerpo ocupe al menos el 100% de la altura de la ventana */
  display: grid; /* Utiliza el modelo de caja de cuadrícula */
  align-content: center; /* Centra verticalmente el contenido dentro de la cuadrícula */
  gap: 2rem; /* Espaciado entre los elementos de la cuadrícula */
  padding: 2rem; /* Espaciado interno alrededor del cuerpo */
  font-family: "Poppins", sans-serif; /* Fuente para todo el texto en la página */
  color: var(--color); /* Aplica el color de texto definido en la variable */
  background: var(--bgColor); /* Aplica el color de fondo definido en la variable */
}

/* Estilos para la lista */
ul {
    margin-top: 2rem;
  --col-gap: 2rem; /* Espacio entre las columnas de la cuadrícula */
  --row-gap: 2rem; /* Espacio entre las filas de la cuadrícula */
  --line-w: 0.25rem; /* Ancho de la línea que conecta los elementos de la lista */
  display: grid; /* Usa un layout de cuadrícula */
  grid-template-columns: var(--line-w) 1fr; /* Define las columnas de la cuadrícula: la primera es la línea y la segunda es el contenido */
  grid-auto-columns: max-content; /* Las columnas se ajustan automáticamente al contenido */
  column-gap: var(--col-gap); /* Espacio entre las columnas */
  list-style: none; /* Elimina las viñetas predeterminadas de la lista */
  width: min(60rem, 90%); /* Limita el ancho de la lista al mínimo entre 60rem y el 90% del ancho de la ventana */
  margin-inline: auto; /* Centra la lista horizontalmente */
}

/* Estilo para la línea vertical que conecta los elementos de la lista */
ul::before {
  content: ""; /* Elemento vacío para crear la línea */
  grid-column: 1; /* Coloca la línea en la primera columna de la cuadrícula */
  grid-row: 1 / span 20; /* La línea se extiende sobre varias filas */
  background: rgb(225, 225, 225); /* Color de la línea */
  border-radius: calc(var(--line-w) / 2); /* Bordes redondeados para la línea */
}

/* Estilo para los elementos de la lista que no son el último */
ul li:not(:last-child) {
  margin-bottom: var(--row-gap); /* Espacio entre los elementos de la lista */
}

/* Estilo para cada ítem de la lista */
ul li {
  grid-column: 2; /* Coloca el contenido en la segunda columna de la cuadrícula */
  --inlineP: 1.5rem; /* Espacio interno horizontal dentro de cada ítem */
  margin-inline: var(--inlineP); /* Margen horizontal para los ítems */
  grid-row: span 2; /* Cada ítem ocupa dos filas en la cuadrícula */
  display: grid; /* Usa un layout de cuadrícula dentro de cada ítem */
  grid-template-rows: min-content min-content min-content; /* Define tres filas de altura mínima */
}

/* Estilo para la fecha dentro de cada ítem */
ul li .fecha {
  --dateH: 3rem; /* Altura de la sección de la fecha */
  height: var(--dateH); /* Aplica la altura definida */
  margin-inline: calc(var(--inlineP) * -1); /* Ajusta el margen horizontal para que la fecha sobresalga */
  text-align: center; /* Centra el texto dentro de la fecha */
  background-color: var(--fecha-color); /* Color de fondo, usando una variable personalizada */
  color: white; /* Color del texto en la fecha */
  font-size: 1.25rem; /* Tamaño del texto */
  font-weight: 700; /* Hace el texto en negrita */
  display: grid; /* Usa un layout de cuadrícula */
  place-content: center; /* Centra el contenido de la fecha */
  position: relative; /* Posiciona la fecha relativa a su contenedor */
  border-radius: calc(var(--dateH) / 2) 0 0 calc(var(--dateH) / 2); /* Bordes redondeados para la fecha */
}

/* Estilo para la parte inferior de la fecha, que parece un triángulo */
ul li .fecha::before {
  content: ""; /* Elemento vacío para crear el triángulo */
  width: var(--inlineP); /* Ancho igual al espacio interno definido */
  aspect-ratio: 1; /* Mantiene una relación de aspecto 1:1 para crear un cuadrado */
  background: var(--fecha-color); /* Usa el color de fondo de la fecha */
  background-image: linear-gradient(rgba(0, 0, 0, 0.2) 100%, transparent); /* Aplica un degradado sutil para dar un efecto de sombra */
  position: absolute; /* Posiciona el triángulo respecto al contenedor de la fecha */
  top: 100%; /* Coloca el triángulo justo debajo de la fecha */
  clip-path: polygon(0 0, 100% 0, 0 100%); /* Recorta el cuadrado para convertirlo en un triángulo */
  right: 0; /* Alinea el triángulo a la derecha de la fecha */
}

/* Estilo para el círculo que conecta la fecha con la línea */
ul li .fecha::after {
  content: ""; /* Elemento vacío para crear el círculo */
  position: absolute; /* Posiciona el círculo respecto al contenedor de la fecha */
  width: 1rem; /* Ancho del círculo */
  aspect-ratio: 1; /* Mantiene una relación de aspecto 1:1 para crear un círculo */
  background: var(--bgColor); /* Color de fondo, utilizando la variable definida */
  border: 0.3rem solid var(--fecha-color); /* Borde del círculo, con el color de la fecha */
  border-radius: 50%; /* Hace que el elemento sea un círculo perfecto */
  top: 50%; /* Centra verticalmente el círculo dentro del contenedor de la fecha */
  transform: translate(50%, -50%); /* Ajusta la posición del círculo para alinearlo correctamente */
  right: calc(100% + var(--col-gap) + var(--line-w) / 2); /* Coloca el círculo a la izquierda de la línea */
}

/* Estilos para el título y la descripción dentro de cada ítem */
ul li .title,
ul li .descripcion {
  background: var(--bgColor); /* Fondo del título y la descripción, usando la variable definida */
  position: relative; /* Posiciona los elementos relativos a su contenedor */
  padding-inline: 1.5rem; /* Espaciado interno horizontal */
}

ul li .title {
  overflow: hidden; /* Oculta cualquier contenido que se desborde */
  padding-block-start: 1.5rem; /* Espaciado interno superior */
  padding-block-end: 1rem; /* Espaciado interno inferior */
  font-weight: 500; /* Hace el texto del título un poco más grueso */
}

ul li .descripcion {
  padding-block-end: 1.5rem; /* Espaciado interno inferior */
  font-weight: 300; /* Hace el texto de la descripción más delgado */
}

/* Estilos para las sombras debajo del título y la descripción */
ul li .title::before,
ul li .descripcion::before {
  content: ""; /* Elemento vacío para crear la sombra */
  position: absolute; /* Posiciona la sombra respecto al contenedor del título o descripción */
  width: 90%; /* Ancho de la sombra */
  height: 0.5rem; /* Altura de la sombra */
  background: rgba(0, 0, 0, 0.5); /* Color de fondo oscuro para simular una sombra */
  left: 50%; /* Centra la sombra horizontalmente */
  border-radius: 50%; /* Bordes redondeados para la sombra */
  filter: blur(4px); /* Aplica un desenfoque para hacer la sombra más suave */
  transform: translate(-50%, 50%); /* Ajusta la posición para centrar la sombra */
}

ul li .title::before {
  bottom: calc(100% + 0.125rem); /* Coloca la sombra debajo del título */
}

ul li .descripcion::before {
  z-index: -1; /* Coloca la sombra detrás del contenido */
  bottom: 0.25rem; /* Coloca la sombra justo*/
}


/* Media query para pantallas anchas (40rem o más) */
@media (min-width: 40rem) {
  ul {
    grid-template-columns: 1fr var(--line-w) 1fr; /* Ajusta la cuadrícula para tener tres columnas */
  }
  ul::before {
    grid-column: 2; /* Mueve la línea vertical a la segunda columna de la cuadrícula */
  }
  ul li:nth-child(odd) {
    grid-column: 1; /* Coloca los ítems impares en la primera columna */
  }
  ul li:nth-child(even) {
    grid-column: 3; /* Coloca los ítems pares en la tercera columna */
  }

  /* Ajuste para que el segundo ítem abarque dos filas */
  ul li:nth-child(2) {
    grid-row: 2/4; /* El segundo ítem ocupará desde la segunda hasta la cuarta fila */
  }

  /* Ajustes específicos para los ítems impares */
  ul li:nth-child(odd) .fecha::before {
    clip-path: polygon(0 0, 100% 0, 100% 100%); /* Invierte el triángulo en los ítems impares */
    left: 0; /* Alinea el triángulo a la izquierda */
  }

  ul li:nth-child(odd) .fecha::after {
    transform: translate(-50%, -50%); /* Ajusta la posición del círculo en los ítems impares */
    left: calc(100% + var(--col-gap) + var(--line-w) / 2); /* Coloca el círculo a la derecha de la línea */
  }

  ul li:nth-child(odd) .fecha {
    border-radius: 0 calc(var(--dateH) / 2) calc(var(--dateH) / 2) 0; /* Ajusta los bordes redondeados para los ítems impares */
  }
}

/* Estilo para los créditos */
.credits {
  margin-top: 1rem; /* Espaciado superior para los créditos */
  text-align: right; /* Alinea el texto de los créditos a la derecha */
}
.credits a {
  color: var(--color); /* Aplica el color de texto definido en la variable */
}
</style>