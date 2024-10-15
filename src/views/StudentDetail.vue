<template>
  <div class="studentDetail">
    <h2>Detay</h2>
   <div v-if="student"> <h3>Öğrenci İsmi: {{student.name}}</h3> <h3>Id: {{id}}</h3></div>
   <div v-else>Loading...</div>
  </div>
</template>

<script>
import axios from 'axios';
export default {
name:'studentDetail',
props:['id'],
data() {
    return {
       student:null,
    }
},
mounted(){
//  fetch('http://localhost:3000/students/'+this.id).then(res=> res.json()).then(data=>this.student=data).catch(err =>console.error(err.message))
axios.get('http://localhost:3000/students/'+this.id)
  .then(res=> this.student = res.data)
  .catch(function (error) {
    console.log(error);
  })
  .finally(function () {
  });
},
}
</script>

<style>

</style>