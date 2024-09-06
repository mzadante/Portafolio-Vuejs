<script setup>
//Se importa ref de vue para poder usarlo
import { ref } from 'vue';
//Se crea un array de objetos con las habilidades
//Este es un array de objetos con habilidades que se pueden modificar o agregar
const habilidades = ref([
    {// Se crea un objeto con id, nombre y habilidades
        id: 1, nombre: 'Lenguajes de Programación', habilidades: [
            //Se crea un objeto con id, nombre, nivel e icono
            { id: 1, nombre: 'JavaScript', nivel: 'Avanzado', icono: '/src/components/icons/js.svg' },
            { id: 2, nombre: 'Python', nivel: 'Intermedio', icono: '/src/components/icons/python.svg' },
            { id: 3, nombre: 'HTML/CSS', nivel: 'Avanzado', icono: '/src/components/icons/html-css.svg' },
            { id: 4, nombre: 'Java', nivel: 'Intermedio', icono: '/src/components/icons/java.svg' },
            { id: 5, nombre: 'SQL', nivel: 'Intermedio', icono: '/src/components/icons/sql.svg' }
        ]
    },
    {
        id: 2, nombre: 'Frameworks y Librerías', habilidades: [
            { id: 1, nombre: 'React.js', nivel: 'Avanzado', icono: '/src/components/icons/react.svg' },
            { id: 2, nombre: 'Vue.js', nivel: 'Intermedio', icono: '/src/components/icons/vue.svg' },
            { id: 3, nombre: 'Node.js', nivel: 'Avanzado', icono: '/src/components/icons/node.svg' },
            { id: 4, nombre: 'Django', nivel: 'Intermedio', icono: '/src/components/icons/django.svg' },
            { id: 5, nombre: 'Bootstrap', nivel: 'Avanzado', icono: '/src/components/icons/bootstrap.svg' }
        ]
    },
    {
        id: 3, nombre: 'Herramientas y Software', habilidades: [
            { id: 1, nombre: 'Git', nivel: 'Avanzado', icono: '/src/components/icons/git.svg' },
            { id: 2, nombre: 'Docker', nivel: 'Intermedio', icono: '/src/components/icons/docker.svg' },
            { id: 3, nombre: 'Cypress', nivel: 'Intermedio', icono: '/src/components/icons/cypress.svg' },
            { id: 4, nombre: 'Figma', nivel: 'Intermedio', icono: '/src/components/icons/figma.svg' },
            { id: 5, nombre: 'Visual Studio Code', nivel: 'Avanzado', icono: '/src/components/icons/visual.svg' }
        ]
    },
    {
        id: 4, nombre: 'Bases de Datos', habilidades: [
            { id: 1, nombre: 'MongoDB', nivel: 'Avanzado', icono: '/src/components/icons/mongo.svg' },
            { id: 2, nombre: 'MySQL', nivel: 'Intermedio', icono: '/src/components/icons/mysql.svg' },
            { id: 3, nombre: 'PostgreSQL', nivel: 'Intermedio', icono: '/src/components/icons/postgres.svg' }
        ]
    },
    {
        id: 5, nombre: 'Idiomas', habilidades: [
            { id: 1, nombre: 'Español', nivel: 'Nativo', icono: '/src/components/icons/arg.svg' },
            { id: 2, nombre: 'Inglés', nivel: 'Avanzado (C1)', icono: '/src/components/icons/eeuu.svg' }
        ]
    }
]);

</script>


<template>
    <!--Este componente vue funciona de esta forma:-->
    <div class="skills-contenedor">
        <!--Se recorre el array habilidades con v-for y se asigna la key habilidad.id-->
        <div v-for="habilidad in habilidades" :key="habilidad.id" class="skills-categoria">
            <!--Se muestra el nombre de la habilidad-->
            <h3>{{ habilidad.nombre }}</h3>
            <ul class="skills">
                <!--Se recorre el array habilidades con v-for y se asigna la key habilidad.id-->
                <li v-for="habilidad in habilidad.habilidades" :key="habilidad.id" class="skill">
                    <!--Se muestra el icono de la habilidad y el nombre de la habilidad con su nivel-->
                    <img :src="habilidad.icono" :alt="habilidad.nombre">
                    <!--Se muestra el icono de la habilidad y el nombre de la habilidad con su nivel-->
                    <span>{{ habilidad.nombre }}: {{ habilidad.nivel }}</span>
                </li>
            </ul>
        </div>
    </div>

    <!-- <div class="skills-contenedor">
        <div class="skills-categoria">
            <h3>Lenguajes de Programación</h3>
            <ul class="skills">
                <li class="skill">
                    <img src="/src/components/icons/js.svg" alt="JavaScript">
                    <span>JavaScript: Avanzado</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/python.svg" alt="Python">
                    <span>Python: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/html-css.svg" alt="HTML/CSS">
                    <span>HTML/CSS: Avanzado</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/java.svg" alt="Java">
                    <span>Java: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/sql.svg" alt="SQL">
                    <span>SQL: Intermedio</span>
                </li>
            </ul>
        </div>

        <div class="skills-categoria">
            <h3>Frameworks y Librerías</h3>
            <ul class="skills">
                <li class="skill">
                    <img src="/src/components/icons/react.svg" alt="React.js">
                    <span>React.js: Avanzado</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/vue.svg" alt="Vue.js">
                    <span>Vue.js: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/node.svg" alt="Node.js">
                    <span>Node.js: Avanzado</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/django.svg" alt="Django">
                    <span>Django: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/bootstrap.svg" alt="Bootstrap">
                    <span>Bootstrap: Avanzado</span>
                </li>
            </ul>
        </div>

        <div class="skills-categoria">
            <h3>Herramientas y Software</h3>
            <ul class="skills">
                <li class="skill">
                    <img src="/src/components/icons/git.svg" alt="Git">
                    <span>Git: Avanzado</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/docker.svg" alt="Docker">
                    <span>Docker: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/cypress.svg" alt="Cypress">
                    <span>Cypress: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/figma.svg" alt="Figma">
                    <span>Figma: Intermedio</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/visual.svg" alt="Visual Studio Code">
                    <span>Visual Studio Code: Avanzado</span>
                </li>
            </ul>
        </div>

        <div class="skills-categoria">
            <h3>Bases de Datos</h3>
            <ul class="skills">
                <div class="skill">
                    <img src="/src/components/icons/mongo.svg" alt="MongoDB">
                    <span>MongoDB: Avanzado</span>
                </div>
                <div class="skill">
                    <img src="/src/components/icons/mysql.svg" alt="MySQL">
                    <span>MySQL: Intermedio</span>
                </div>
                <div class="skill">
                    <img src="/src/components/icons/postgres.svg" alt="PostgreSQL">
                    <span>PostgreSQL: Intermedio</span>
                </div>
            </ul>
        </div>

        <div class="skills-categoria">
            <h3>Idiomas</h3>
            <ul class="skills">
                <li class="skill">
                    <img src="/src/components/icons/arg.svg" alt="Español">
                    <span>Español: Nativo</span>
                </li>
                <li class="skill">
                    <img src="/src/components/icons/eeuu.svg" alt="Inglés">
                    <span>Inglés: Avanzado (C1)</span>
                </li>
            </ul>
        </div>
    </div> -->
</template>

<style scoped>
.skills-contenedor {
    padding: 2rem;
    /*Fondo cargado desde una imagen estatica en Assets*/
    /* background-image: url('/src/assets/fondo-proyectos.jpg');
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat; */
    /*Fondo con gradiente*/
    background: linear-gradient(-45deg, #021526, #03346E, #6EACDA, #E2E2B6);
    /*Fondo con color solido*/
    /* background-color: rgb(28, 41, 52); */
}

.skills-categoria {
    margin-bottom: 20px;
}

.skills-categoria h3 {
    display: flex;
    justify-content: left;
    margin-bottom: 10px;
    font-size: 1.5em;
    color: aliceblue;
    font-size: 1.5em;
    font-weight: bold;
}

.skills {
    display: flex;
    justify-content: space-evenly;
    flex-wrap: wrap;
    gap: 20px;
}

.skill {
    display: flex;
    justify-content: center;
    align-items: center;
    gap: 10px;
    background-color: rgba(241, 245, 243, 0.856);
    padding: 0.3em;
    border-radius: 8px;
    box-shadow: 0px 4px 12px rgba(2, 151, 151, 0.963);
    flex: 1 1 200px;
    max-width: 250px;
}

.skill:hover {
    background-color: rgba(2, 151, 151, 0.963);
}

.skill img {
    width: 35px;
    height: 35px;
}

.skill span {
    font-size: 1em;
    color: #333;
}

.skill:hover {
    font-size: 1.3em;
    transition: 2s ease;
}

@media (max-width: 768px) {
    .skills-categoria h3 {
        justify-content: center;
    }

    .skill {
        justify-content: center;
    }
}
</style>