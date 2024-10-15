<template>
  <div>
  <nav>
    <router-link to="/">Home</router-link> |
    <router-link to="/about">About</router-link> |
    <router-link :to="{name:'studentView'}">Students</router-link> 
  </nav>
  <div>
    <button @click="mainPage()">Ana Sayfa</button>
    <button @click="back()">Geri Git</button>
    <button @click="next()">İleri</button>
  </div>
  <router-view/>
</div>
</template>
<script>
export default {
methods:{
  mainPage(){
    this.$router.push('/')
  },
  back(){
this.$router.go(-1);
  },
  next(){
    this.$router.go(+1);
  }
}
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}

nav {
  padding: 30px;
}

nav a {
  font-weight: bold;
  color: #2c3e50;
}

nav a.router-link-exact-active {
  color: #42b983;
}

button{
  margin: 0px 20px;
  padding: 10px;
  border-radius: 20px;
  border: none;
  cursor: pointer;
}
.studentDetail, .student{
  box-shadow: rgba(100, 100, 111, 0.2) 0px 7px 29px 0px;
  max-width: 600px;
  width: 100%;
  padding: 30px;
  border-radius: 20px;
  margin: 20px auto;
}
</style>
