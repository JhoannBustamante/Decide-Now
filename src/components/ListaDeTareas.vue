<template>
    <div>
        <h2>Lista de tareas</h2>
        <input type="text" placeholder="Escribe una tarea" v-model="nuevaTarea" @keyup.enter="agregarTarea">
        <ul>
            <li v-for="(tarea, index) in tareas" :key="index">
                {{ tarea }}
            </li>
        </ul>
    </div>
</template>
    
<script setup>
import { ref } from 'vue'
const tareas = ref([]);
const nuevaTarea = ref('');
const agregarTarea = () => {
    tareas.value.push(nuevaTarea.value);
    nuevaTarea.value = '';
}

</script>

<style scoped>

</style>
