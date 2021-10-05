<template>
    <div class="estrutura-tasks">
        <label v-for="task of tarefas" :key="task" class="label-task" :class=" { riscado: task.checked } ">
            {{ task.tarefa }}
            <input type="checkbox" v-model="task.checked">
        </label>
    </div>
</template>

<script>
export default {
    props: ['tarefas'],
}
</script>

<style>
.estrutura-tasks {
    padding: 30px;
    display: flex;
    flex-flow: column;
    gap: 10px;
}
.label-task {
    padding: 5px 30px;
}
.riscado {
    color: lightgray;
    text-decoration: line-through;
}
</style>