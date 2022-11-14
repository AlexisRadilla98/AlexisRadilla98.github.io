<template>
    <div>
        <h1> Alexis Radilla </h1>
        <input type="text" v-model="input">
        
        <ul>
            <li v-for="(name, index) in filteredNames" v-bind:key="index">
                {{name}}
            </li>
        </ul>
        
    </div>
    
</template>
<script>
export default {
  name: 'userName',
  data(){
    return{
        names:[
            'Parth',
            'Eduard',
            'Frank',
            'Edger',
            'Max',
            'Chencho',
            'Demian',
            'Alexis',
            'Citlali',
            'Luz',
            'Juan'
        ],
        input:''
    }
  },
  computed:{
    filteredNames(){
        return this.input !== ''? this.names.filter(name=>name.toLocaleLowerCase().includes(this.input.toLocaleLowerCase())):''
    }
  }
} 
</script>
<style scoped>
*{
    background-color: palevioletred;
}
h1{
    font-size: 20px;
}
div{
    font-size: 18px;
}
ul{
    width: 80%;
    display: list-item;
    flex-direction: column;
    justify-content: center;
    margin-left: 07vw;
    padding: 5px;
}
ul>li{
    color: aqua;
    background-color: rgb(159, 127, 255);
    box-shadow: 3px 3px 3px -3px;
    list-style: none;
    margin: 10px;
    border-radius: 3px;
    height: 40px;
    
    padding: 5px;
}
input{
    background-color: aliceblue;
    width: 90%;
    height: 100%;
}
</style>