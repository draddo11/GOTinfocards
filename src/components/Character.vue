<template>
    <div class='col-md-4' @click='switchCharacter'>
            click on card for more characters
        <div class ='character-card'>
            <div class='card-block'>
            <h4 class='card-title'>{{character.name}}</h4>
            <p class='card-text'> Gender:{{character.gender}}</p>
            <p class='card-text'>Born:{{character.born}}</p>
            <p class='card-text'>Titles:{{character.titles}}</p>
            <p class='card-text'>Aliases:{{character.aliases}}</p>
            <p class='card-text'>Played By:{{character.playedBy}}</p>
            <p class='card-text'>TV Series:{{character.tvSeries}}</p>
            <p class='card-title'>Culture:{{character.culture}}</p>

            </div>
        </div>
    </div>
</template>
<script>
export default {
    props:['id'],
   data(){
       return {
           character:{}
       }
   } ,
   methods:{
       fetchCharacter(id){
           fetch(`https://anapioficeandfire.com/api/characters/${id}`,{
               method:'GET'
           })
           .then(response => response.json())
           .then(json => this.character=json)
       },
       switchCharacter(){
           let random_id = Math.floor(Math.random() * 538) + 1
           this.fetchCharacter(random_id)
       }
   }, 
   created(){
       this.fetchCharacter(this.id)
   }
}
</script>
