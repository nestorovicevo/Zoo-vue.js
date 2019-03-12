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
        <td>{{animal.birthday}}</td>
      </tr>
    </table>
  </div>
</template>

<script>
export default {
  data(){
    return{
      animals : [{specie:"Snake", name:"Cruela", birthday:"20.03.2010"},
         {specie:"Bear", name:"Baloo", birthday:"23.082015"},
         {specie:"Tiger", name:"Kan", birthday:"30.05.2013"},
         {specie:"Cat", name:"Tom", birthday:"15.04.2012"},
         {specie:"Dog", name:"Sargo", birthday:"10.02.2018"}]
    }
  }
}
</script>

<style>

</style>
