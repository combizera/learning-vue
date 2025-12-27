<template>
  <div class="task-list-container">
    <h2>
      Lista de Tarefas
    </h2>

    <div class="controls">
      <button class="btn-add">
        Adicionar Nova Tarefa
      </button>
      <div class="btn-toggle-all">
        Marcar Todas
      </div>
      <button class="btn-clear">
        Limpar Concluídas
      </button>
    </div>

    <div class="tasks-container">
      <div class="pending-tasks">
        <h3>
          Tarefas Pendentes
        </h3>
        <TaskItem />
      </div>

      <div class="completed-tasks">
        <h3>
          Tarefas Concluídas
        </h3>
        <TaskItem />
      </div>

      <span>
        Aqui virá o componente de contadores
      </span>
    </div>
  </div>
</template>

<script>
import TaskItem from './TaskItem.vue';

  export default {
    name: 'TaskList',
    components: {
      TaskItem
    }
  }
</script>

<style>
  .task-list-container {
    max-width: 1000px;
    margin: 0 auto;
    padding: 20px;
    }
    h2 {
      color: #3498db;
      margin-bottom: 20px;
      padding-bottom: 20px;
      border-bottom: 2px solid #f0f0f0;
    }
    .controls {
      display: flex;
      gap: 10px;
      margin-bottom: 10px;
      flex-wrap: wrap;
      justify-content: center;
    }
    button {
      padding: 10px 20px;
      border: none;
      border-radius: 6px;
      cursor: pointer;
      font-weight: bold;
      transition: .3s all;
      font-size: 1rem;
    }
    .btn-add {
      background-color: #2ecc71;
      color: white;
    }
    .btn-add:hover {
      background-color: #27ae60;
    }
    .btn-clear {
      background-color: #e74c3c;
      color: white;
    }
    .btn-clear:hover {
      background-color: #c0392b;
    }
    .btn-toggle-all {
      background-color: #3498db;
      color: white;
    }
    .btn-toggle-all:hover {
      background-color: #2980b9;
    }
    .tasks-container {
      display: grid;
      grid-template-columns: 1fr 1fr;
      gap: 30px;
    }
    .pending-tasks, .completed-tasks {
      padding: 20px;
      border-radius: 8px;
    }
    .pending-tasks {
      background-color: #f9f9f9;
      border: 1px solid #eee;
    }
    .completed-tasks {
      background-color: #f0fff0;
      border: 1px solid #ddd;
    }
    .pending-tasks h3, .completed-tasks h3 {
      margin-top: 0;
      margin-bottom: 10px;
      color: #2c3e50;
      text-align: center;
    }
</style>