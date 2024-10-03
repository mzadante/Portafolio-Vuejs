<script setup>

</script>

<template>
    <div class="galeria">
        <div class="proyecto">
            <img src="/src/assets/annidada-tech.jpeg" alt="Proyecto 1">
            <div class="proyecto-info">
                <h3>Ecomerce </h3>
                <p>Creé una plataforma de comercio electrónico que incrementó las ventas en un 35% durante el
                    primer año.</p>
                <div class="proyecto-links">
                    <a href="https://proyecto1.com" class="btn-ver-mas" target="_blank" rel="noopener noreferrer">Ver
                        Proyecto</a>
                    <a href="https://github.com/usuario/proyecto1" class="github-link" target="_blank"
                        rel="noopener noreferrer">Ver Código en GitHub</a>
                </div>
            </div>
        </div>
        <div class="proyecto">
            <img src="/src/assets/annidada-tech.jpeg" alt="Proyecto 1">
            <div class="proyecto-info">
                <h3>Ecomerce </h3>
                <p>Creé una plataforma de comercio electrónico que incrementó las ventas en un 35% durante el
                    primer año.</p>
                <div class="proyecto-links">
                    <a href="https://proyecto1.com" class="btn-ver-mas" target="_blank" rel="noopener noreferrer">Ver
                        Proyecto</a>
                    <a href="https://github.com/usuario/proyecto1" class="github-link" target="_blank"
                        rel="noopener noreferrer">Ver Código en GitHub</a>
                </div>
            </div>
        </div>
        <div class="proyecto">
            <img src="/src/assets/annidada-tech.jpeg" alt="Proyecto 1">
            <div class="proyecto-info">
                <h3>Ecomerce </h3>
                <p>Creé una plataforma de comercio electrónico que incrementó las ventas en un 35% durante el
                    primer año.</p>
                <div class="proyecto-links">
                    <a href="https://proyecto1.com" class="btn-ver-mas" target="_blank" rel="noopener noreferrer">Ver
                        Proyecto</a>
                    <a href="https://github.com/usuario/proyecto1" class="github-link" target="_blank"
                        rel="noopener noreferrer">Ver Código en GitHub</a>
                </div>
            </div>
        </div>
    </div>

</template>

<style scoped>
/* .galeria {
    width: 100%;
    height: 100vh;
    display: flex;
    flex-wrap: wrap;
    gap: 20px;
    justify-content: center;
    background-image: url('/src/assets/fondo-proyectos.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
} */

/* Estilos Fondo Animado de Css de la galería */
/* La clase 'galeria' es el contenedor principal de la galería de proyectos */
.galeria {
    /* Establece el ancho de la galería al 100% del contenedor padre */
    width: 100%;
    /* Establece la altura de la galería al 100% del contenedor padre */
    height: 100%;
    /* Utiliza flexbox para organizar los elementos hijos en la galería */
    display: flex;
    /* Permite que los elementos se ajusten y pasen a la siguiente línea si no caben en una sola fila */
    flex-wrap: wrap;
    /* Establece un espacio de 20px entre los elementos de la galería */
    gap: 20px;
    /* Agrega un padding de 20px alrededor de la galería */
    padding: 20px;
    /* Centra los elementos hijos horizontalmente */
    justify-content: center;
    /* Aplica un fondo con un degradado de colores */
    background: linear-gradient(-45deg, #021526, #03346E, #6EACDA, #E2E2B6);
    /* Ajusta el tamaño del fondo para que cubra el área completa */
    background-size: 400% 400%;
    /* Aplica una animación al fondo que dura 15 segundos, tiene una transición suave y se repite infinitamente */
    animation: gradient 15s ease infinite;
}

/* Define una animación llamada 'gradient' para cambiar la posición del fondo */
@keyframes gradient {

    /* Al inicio, el fondo está posicionado en el 0% horizontal y 50% vertical */
    0% {
        background-position: 0% 50%;
    }

    /* A la mitad de la animación, el fondo se desplaza al 100% horizontal y 50% vertical */
    50% {
        background-position: 100% 50%;
    }

    /* Al final, el fondo vuelve a la posición inicial */
    100% {
        background-position: 0% 50%;
    }
}

/* La clase 'proyecto' es el contenedor individual de cada proyecto */
.proyecto {
    /* Utiliza flexbox para organizar el contenido del proyecto en una columna */
    display: flex;
    /* Establece la dirección de los elementos en columna */
    flex-direction: column;
    /* Aplica un borde de 2px sólido y color gris claro (#ddd) alrededor del proyecto */
    border: 2px solid #ddd;
    /* Redondea las esquinas del contenedor */
    border-radius: 8px;
    /* Oculta cualquier contenido que se desborde del contenedor */
    overflow: hidden;
    /* Establece un color de fondo claro para el proyecto */
    background-color: #f9f9f9;
    /* Define el ancho máximo del proyecto en 222px */
    max-width: 222px;
    /* Hace que el contenedor se ajuste flexiblemente ocupando al menos 300px de ancho */
    flex: 1 1 300px;
}

/* Estilo para las imágenes dentro del contenedor 'proyecto' */
.proyecto img {
    /* Hace que la imagen ocupe el 100% del ancho del contenedor */
    width: 100%;
    /* Mantiene la relación de aspecto de la imagen */
    height: auto;
    /* Asegura que la imagen se muestre como un bloque, sin espacio en línea alrededor */
    display: block;
}

/* La clase 'proyecto-info' contiene la información del proyecto */
.proyecto-info {
    /* Agrega un padding de 15px alrededor de la información */
    padding: 15px;
    /* Centra el texto dentro del contenedor */
    text-align: center;
}

/* Estilo para los títulos de los proyectos */
.proyecto-info h3 {
    /* Establece un margen superior e inferior de 10px */
    margin: 10px 0;
    /* Define el tamaño de la fuente a 1.3em (relativo al tamaño de fuente del contenedor) */
    font-size: 1.3em;
    /* Aplica un color gris oscuro (#333) al texto */
    color: #333;
}

/* Estilo para los párrafos de los proyectos */
.proyecto-info p {
    /* Establece un margen superior e inferior de 10px */
    margin: 10px 0;
    /* Define el tamaño de la fuente a 1em (igual al tamaño de fuente base) */
    font-size: 1em;
    /* Aplica un color gris (#666) al texto */
    color: #666;
}

/* La clase 'proyecto-links' organiza los enlaces y botones del proyecto */
.proyecto-links {
    /* Utiliza flexbox para organizar los enlaces en una columna */
    display: flex;
    /* Establece la dirección de los elementos en columna */
    flex-direction: column;
    /* Establece un espacio de 10px entre los elementos */
    gap: 10px;
    /* Agrega un margen superior de 10px */
    margin-top: 10px;
}

/* Estilo para el botón 'Ver Más' dentro de la clase 'proyecto-links' */
.proyecto-links .btn-ver-mas {
    /* Aplica un color de fondo azul (#007BFF) */
    background-color: #007BFF;
    /* Aplica un color de texto blanco */
    color: #fff;
    /* Agrega un padding de 10px en vertical y 15px en horizontal */
    padding: 10px 15px;
    /* Redondea las esquinas del botón */
    border-radius: 5px;
    /* Elimina el subrayado del texto */
    text-decoration: none;
    /* Aplica una transición suave al cambiar el color de fondo */
    transition: background-color 0.3s;
}

/* Estilo para cuando el botón 'Ver Más' es hover */
.proyecto-links .btn-ver-mas:hover {
    /* Cambia el color de fondo a un azul más oscuro (#0056b3) */
    background-color: #0056b3;
}

/* Estilo para el enlace a GitHub dentro de la clase 'proyecto-links' */
.proyecto-links .github-link {
    /* Aplica un color gris oscuro (#333) al texto */
    color: #333;
    /* Elimina el subrayado del texto */
    text-decoration: none;
    /* Establece el tamaño de fuente a 0.9em (un poco más pequeño que el tamaño base) */
    font-size: 0.9em;
}

/* Estilo para cuando el enlace a GitHub es hover */
.proyecto-links .github-link:hover {
    /* Añade un subrayado al texto */
    text-decoration: underline;
}
</style>