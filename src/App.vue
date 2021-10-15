<template>
<div>
  <div id="app">
      <input type="text" v-on:keyup.enter="funct" v-model="user.name" style="width: 400px; height: 30px; padding: 30px; background: #fbfbfb">
      <button @click="funct('Juma')" type="button">Submit</button>
  </div>
     <p v-for="(item, index) in lopper" :key="item" @click="lopper = lopper.filter(el => el !== item)">
       <span v-if="item == 3">Hello babies {{ index }}</span>
       <span v-else>{{ item }}</span>

     </p>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'App',
  data () {
    return {
      user: {
        name: '',
        surname: ''
      },
      box: `<div style="width: 200px; height: 300px; background: red">hello car</div>`,
      lopper: [2,3,45,34]
    }
  },
  watch: {
     ['user.name'](arg) {
       console.log(arg)
       this.user.name = arg + '2'
    }
  },
  methods: {
    funct() {
      console.log(this.user)
      this.lopper.push(this.user.name)
      this.user = {}
    },
    functionList (event) {
      console.log(event)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  display: flex;
  flex-direction: row;
  justify-content: center;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
