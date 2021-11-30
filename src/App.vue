<template>
  <div id="app">
    <header class="top">
          <button class="call" @click="callPopup">Добавить пользователя</button>
    </header>
    <Table :table="table" />
    <Popup :table="table" />
  </div>
</template>

<script>
import Table from './components/Table.vue'
import Popup from './components/Popup.vue'

export default {
  name: 'App',
  data(){
    return{
      table:[],
    }
  },
  mounted() {
    this.table = JSON.parse(localStorage.getItem("table")) || []
  },
  methods: {
    callPopup(){
      let pop = document.querySelector('.popup');
      pop.classList.toggle('active')
    },
  },
  components: {
    Table, Popup
  }
}
</script>

<style>
body{
  overflow: hidden;
}
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin: 0 auto;
}

.top{
  width: 800px;
  margin: 0 auto;
  display: flex;
  justify-content: flex-end;
  margin-bottom: 20px;
}
.active{
  opacity: 1;
  right: 20px;
}

.call{
  padding: 10px;
  border: none;
  background: orange;
  border-radius: 5px;
  color: #fff;
  cursor: pointer
}
</style>
