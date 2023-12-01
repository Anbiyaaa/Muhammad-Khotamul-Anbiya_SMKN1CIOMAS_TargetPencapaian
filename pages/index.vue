<template>
  <main>
    <h1 class="stroke">Target Pencapaian</h1>
    <p>Buat List Target Pencapaian</p>

    <div class="create-new">
      <input type="text" v-model="newTask" placeholder=" Target Bulan Ini" @keypress.enter="addTask" />
      <button @click="addTask">Tambah</button>
    </div>

    <div class="tasks">
      <Task v-for="(task, i) in $store.state.tasks" :key="i" :task="task" />
    </div>

    <div class="isi">
      <svg class="img" viewBox="0 0 200 200" xmlns="http://www.w3.org/2000/svg">
        <path fill="#A7F0BA"
          d="M37.1,-64.2C48.7,-57.7,58.9,-48.8,66.9,-37.7C74.8,-26.6,80.3,-13.3,79,-0.8C77.7,11.8,69.5,23.6,62.2,35.7C54.9,47.8,48.4,60.3,38.2,65.3C28,70.3,14,67.9,1.2,65.8C-11.6,63.7,-23.2,61.9,-35.3,58C-47.5,54.2,-60.4,48.2,-68.1,38.2C-75.9,28.2,-78.6,14.1,-77.4,0.7C-76.2,-12.7,-71,-25.4,-65.7,-39.5C-60.3,-53.6,-54.6,-69.2,-43.6,-76.1C-32.6,-83,-16.3,-81.2,-1.8,-78.2C12.8,-75.1,25.6,-70.8,37.1,-64.2Z"
          transform="translate(100 100)" />
      </svg>
    </div>
  </main>
</template>

<script>
export default {
  data() {
    return {
      newTask: ''
    }
  },
  methods: {
    addTask() {
      if (this.newTask) {
        this.$store.commit('ADD_TASK', this.newTask);
        this.newTask = '';
      }
    }
  }
}
</script>
