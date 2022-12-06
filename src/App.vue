<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App" />

</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Web3 from 'web3'
export default {
  name: 'App',
  components: {
    // HelloWorld
  },
  data() {
    return {
      web3: 'this is web3'
    }
  },
  mounted() {
    this.initWeb3()
  },
  methods: {
    initWeb3() {
      //本地私有网络地址
      let host = "http://127.0.0.1:8545"
      //创建providers
      const httpprovi = new Web3.providers.HttpProvider(host)
      this.web3 = new Web3(httpprovi)
      console.log(this.web3)
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
  margin-top: 60px;
}
</style>
