<template>
    <li>
        {{ tarea }}
        <button @click="$emit('eliminar')">Eliminar</button>
    </li>

</template>

<style> </style>

<script>
export default {
    props: {
        tarea: String,
    }
}

</script>