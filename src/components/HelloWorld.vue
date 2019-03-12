<template>
  <div>
    <table style="width:100%">
      <tr>
        <th>Specie</th>
        <th>Name</th> 
        <th>Birthday</th>
      </tr>
      <tr v-for="animal in animals" :key="animal">
        <td>{{animal.specie}}</td>
        <td>{{animal.name}}</td>
        <td>{{animal.birthday? animal.birthday : 'Unknown'}}</td>
        <button @click="removeAnimal(index)">Remove</button>
        <button @click="moveToTop(index)">Move to top</button>
        
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  data(){
    return{
      animals : [{specie:"Snake", name:"Cruela", birthday:"20.03.2010"},
         {specie:"Bear", name:"Baloo", birthday:""},
         {specie:"Tiger", name:"Kan", birthday:"30.05.2013"},
         {specie:"Cat", name:"Tom", birthday:"15.04.2012"},
         {specie:"Dog", name:"Sargo", birthday:"10.02.2018"}]
    }
  },

  methods: {
   moveToTop(index) {
        const animal = this.animals[index];
        this.animals.splice(index,1);
        this.animals = [
          animal, ...this.animals
     ]
   },

    removeAnimal(index){
      this.animals.splice(index, 1);
    }
  }
}
</script>

<style>

</style>
