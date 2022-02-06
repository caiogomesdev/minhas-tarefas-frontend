<template>
    <div id="task">
            <form @submit.prevent="additem()">
                <input type="text" placeholder="tarefa de hoje" v-model="tarefa"/>
                <button type="submit">Adicionar</button>
            </form>
            <Item :lista="tarefas" :concluido="completedTask"/>
    </div>
</template>

<script>
import Item from "./Item.vue"

export default{
    name: "task",
    components:{
        Item
    },
    data(){
        return{
            tarefa: '',
            tarefas: []
        }
    },
    methods:{
        additem(){
            if(this.tarefa === '' || this.tarefa === ' '){
                alert("Digite uma tarefa")
                return;
            }
            this.tarefas.unshift({text: this.tarefa, key: Date.now()})
            this.tarefa = ''
        },
        completedTask(index){
            this.tarefas.splice(index,1)
        }
    }
}
</script>


<style scoped>
    #task{
        max-width: 700px;
        background: #fff;
        border-radius: 4px;
        padding: 20px;
        margin: 20px auto;
        box-shadow: 0px 0px 20px rgba(0,0,0,.2);
    }
    form{
        margin-top: 30px;
        display: flex;
        flex-direction: row;
    }
    form button{
        cursor: pointer;
        background: #0F5959;
        border: 0;
        border-radius: 4px;
        margin-left: 3px;
        padding: 0 15px;
        
        display: flex;
        justify-content: center;
        align-items: center;
        font-size: 14px;
        color: #fff;
    }
    input{
        flex: 1;
        border: 1px solid #eee;
        padding: 6px 10px;
        font-size: 14px;
        outline: none;
    }
</style>