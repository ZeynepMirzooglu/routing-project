<template>
    <div>
  <h2>Öğrencilerim</h2>
 <div v-for="student in students" :key="student.id">
    <router-link :to="{name:'studentDetail',params:{id:student.id}}"> <h2>{{student.name}}</h2></router-link>
 </div>
</div>
</template>

<script>
export default {
name:'studentView',
components:{

},
data() {
    return {
        students:[
            {name:'Aslan Aslan', id:1},
            {name:'Ali Aslan', id:2}
        ]
    }
},
}
</script>

<style>

</style>