<template>
  <div id="app">
    <header class="header">
      <h1>Bem vindo à minha lista de tarefas!</h1>
      <div class="label-input">
        <label for="input">Adicione uma tarefa no input abaixo (Enter para adicionar)</label>
        <input type="text" v-model="novaTarefa" @keyup.enter="adicionarTarefa">
      </div>
    </header>
    <RenderizedTasks :tarefas="tarefas"></RenderizedTasks>
  </div>
</template>

<script>
import RenderizedTasks from './components/renderizedtasks'

export default {
  name: 'App',
  components: {RenderizedTasks},
  data() {
    return {
      nome: '',
      novaTarefa: '',
      tarefas: [],
    }
  },
  methods: {
    adicionarTarefa() {
      this.tarefas.push({
        tarefa: this.novaTarefa,
        checked: false
      })
      this.novaTarefa = '';
    }
  },
}
</script>

<style>
* {
  font-family: Arial, Helvetica, sans-serif;
  box-sizing: border-box;
  padding: 0;
  margin: 0;
}
.header {
  padding: 30px;
  background: tomato;
}
.label-input {
  gap: 5px;
  color: white;
  display: flex;
  flex-flow: column nowrap;
}
.label-input input {
  display: inline-block;
  padding: 3px 15px;
  width: 600px;
}
h1 {
  font-size: 3em;
  color: white;
}
</style>
