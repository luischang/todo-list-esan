<template>
    <h1> Hola ESAN </h1>
    <input v-model="nuevaTarea" 
        placeholder="Nueva tarea" 
        @keyup.enter="agregarTarea"/>
    <button @click="agregarTarea">
        Agregar
    </button>

    <div v-if="tareas.length === 0">
            No se encontraron tareas
    </div>
    <ul v-else>
        Existen {{tareas.length}} tareas
        <ToDoItem
            v-for="(tarea, index) in tareas"
            :key="index"
            :tarea="tarea" 
            @eliminar="eliminarTarea(index)"
        />
    </ul>

</template>

<style>
</style>

<script> 
import ToDoItem from './ToDoItem.vue'
export default {
    components: {
        ToDoItem
    },
    data(){
        return {
            nuevaTarea:'',
            tareas: []
        }
    },
    methods : {
        agregarTarea(){
            console.log("Aqui agregaremos las tareas: " + this.nuevaTarea);
            this.tareas.push(this.nuevaTarea)
            this.nuevaTarea = ''
        },
        eliminarTarea(index){
            this.tareas.splice(index, 1)
        }
    }
}


</script>