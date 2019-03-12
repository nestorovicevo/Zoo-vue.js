<template>
  <div>

    <form @submit.prevent="addAnimal">
      <div>
        Field:<br>
        <select v-model="animal.sector">
          <option v-for="sector in sectors" :key="sector" :value="sector">{{sector}}</option>
        </select>
        <br>
        Species:<br>
        <input type="text" v-model="animal.species" name="species">
        <br>
        Name:<br>
        <input type="text" v-model="animal.name" name="name">
        <br>
        Birthday:<br>
        <input type="text" v-model="animal.birthday" name="birthday">
        <br>
      </div>
     <button type="submit">Add animal</button>
    </form>

    <table style="width:100%">
      <tr>
        <th>species</th>
        <th>Name</th> 
        <th>Birthday</th>
        <th>Sector</th>
      </tr>
      <tr v-for="(animal, index) in animals" :key="animal">
        <td>{{animal.species}}</td>
        <td>{{animal.name}}</td>
        <td>{{animal.birthday? animal.birthday : 'Unknown'}}</td>
        <td>{{animal.sector}}</td>
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
      animals : [{species:"Snake", name:"Cruela", birthday:"20.03.2010"},
         {species:"Bear", name:"Baloo", birthday:""},
         {species:"Tiger", name:"Kan", birthday:"30.05.2013"},
         {species:"Cat", name:"Tom", birthday:"15.04.2012"},
         {species:"Dog", name:"Sargo", birthday:"10.02.2018"}],
    
       animal : {
        name : '',
        species : '',
        birthday : '',
        sector: ''
        },

        sectors : [
          'divlje zivotinje', 'domace zivotinje'
        ]
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
    },

    addAnimal(){
      this.animals.push({...this.animal});

    
    }
  }
}
</script>

<style>

</style>
