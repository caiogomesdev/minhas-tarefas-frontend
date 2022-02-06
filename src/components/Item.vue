<template>
    <div id="item">
        <ul>
            <li v-for="(task, i) in lista" :key="task.key"> <span>{{task.text}}</span><button @click="concluir(i)" >concluir</button></li>
        </ul>

    </div>
    
</template>


<script>

export default {
    name: "Item",
    props:['lista', 'concluido'],
    methods: {
        concluir(id){
            this.concluido(id)

        }
    }
        
    
}
</script>

<style scoped>
#{
    white-space: pre-wrap;
    word-break: break-word;
}
ul{
    list-style: none;
    margin-top: 20px;
}
ul li{
    padding: 15px 0px;
    display: flex;
    flex-direction: row;
    align-items: center;
    justify-content: space-between;
}
li:not(:first-child){
    border-top: 1px solid #EEE;
}
span{
    color: #0D2636;
}
button{
    cursor: pointer;
    background-color: #DDD;
    color: #000;
    padding: 8px 7px;
    outline: 0;
    border: none;
    border-radius: 4px;
}
</style>