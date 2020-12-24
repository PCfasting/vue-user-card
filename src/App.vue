<template>
  <div id="app">
    <HelloWorld v-bind:value="info"/>
    <button v-on:click="getUserData">Обновить</button>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  components: {
    HelloWorld
  },
  data(){
    return {
      info: {
        link_img: " ",
        nickname: " ",
        name: " ",
        address: " ",
        email: " ",
        number: " "
      }
    }
  },
  methods:{
    getUserData(){
      this.axios.get('http://37.77.104.246/users/getrandom.php')
        .then((response)=>{
          this.info.link_img = response.data.img;
          this.info.nickname = response.data.firstName;
          this.info.name = response.data.lastName;
          this.info.email = response.data.email;
          this.info.number = response.data.phone;
          this.info.address = response.data.city + " " +  response.data.street + " " + response.data.houseNumber;
        })
    },
  },
  mounted(){
    this.getUserData();
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
  margin-top: 60px;
}
</style>
