<template>
<div>
    
    <h1>The Rick and Morty charactors</h1>
    <div v-for="character in characters.results" :key="character.id">
        <div class="BD">
            
            <br>
            <img :src="character.image" alt="">
        </div>
        <div class="BD2">
            <div class="BD2">
                <h3 class="link">{{character.name}}</h3>
            <ul>
            <li><span class="green" id="status" v-if="character.status=='Alive'"></span> 
                <span class="red" id="status" v-else-if="character.status=='Dead'"></span>
                <span class="blue" id="status" v-if="character.status=='unknown'"></span>
                Status: {{character.status}}</li>
            <li>Species: {{character.species}}</li>
            <li>Gender: {{character.gender}}</li>
            <li>No. Episodes: {{character.episode.length}}</li>
            <li>Created Date: {{character.created}}</li>
        </ul>
            </div>
            
        </div>
    </div>
    <div></div>
</div>
</template>
<script>
export default {
    name: 'rickAndMorty',
    data(){
        return{
            characters:[]
        }
    },
    methods:{
        callingAPI(){
            fetch("https://rickandmortyapi.com/api/character").then(res=>res.json().then((data)=>{
                this.characters=data
            }))
        },
        Largo(){
        return this.list.length
    }
    },
    mounted(){
        this.callingAPI()
    }
    
}
</script>
<style scoped>
*{
    background-image:"https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcT1mpZWutgHb5cCDwCxEZu2eM4ZhPlbAiibEgSK-PDz&s"
}
h1{color: rgb(241, 241, 243);}
div{
    display: inline-block;
    justify-content: left;
    background-color: black;
    color: gold;
    margin-bottom: 10px;
}
.BD{
    display: flex;
    background-color: rgb(68, 72, 72);
    border-radius: 5px;
    color: rgb(21, 21, 20);
}
.BD2{
    display: flex;
    flex-direction: column;
    background-color: rgb(83, 76, 76);
    border-radius: 5px;
    color: gold;
    margin-left: 5px;
    margin-right: 5px;
}
.link:hover{
    color:gold
}
#status{
    height: 10px;
    width: 10px;
    border-radius: 50%;
    display: inline-block;
}
.green{
    background-color: green;
}
.red{
    background-color: red;
}
.blue{
    background-color: blue;
}
div>ul{
    margin-bottom: 0px;
    margin-top: 0px;
    list-style: none;
    padding: 0px;
}
div>img{
    margin-left: 10px;
    margin-right: 10px;
    justify-content: left;
}
div>h3{
    color: aliceblue;
}
</style>