<template>
  <div id="app">
    <header>Minhas tarefas</header>
    <Task />
  </div>
</template>

<script>
import Task from "./components/Task.vue"
export default {
    name:"App",
    components:{
      Task    
    },
    data(){
      return{

      }
    },
    methods:{

    },
    
  }

</script>
  
<style scoped>

header{
  display: flex;
  width: 100%;
  justify-content: center;
  align-items: center;
  height: 80px;
  font-size: 40px;
  color: #fff;
}

</style>
