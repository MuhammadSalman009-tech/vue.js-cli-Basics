<template>
  <p>this is body paragraph element</p>
  <teleport to=".modals" v-if="isOpen">
    <Modal :header="header" @closeModal="toggleModal">
      <h1>this is first modal</h1>
      <template v-slot:links>
        <a href="/">Sign Up</a> <br><br>
        <a href="/">Sign In</a>
      </template>
    </Modal>
  </teleport>
  <div v-if="isOpen2">
    <Modal :header="header" @closeModal="toggleModal2">
      <h1>this is 2nd modal</h1>
      <template v-slot:links>
        <a href="/">Sign Up</a> <br><br>
        <a href="/">Sign In</a>
      </template>
    </Modal>
  </div>
  
  <br>
  <button @click="toggleModal">Open Modal</button>
    <button @click="toggleModal2">Open Modal2</button>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Modal from  "./components/Modal";

export default {
  data(){
    return{
      title:"salman",
      header:"this is header prop",
      footer:"this is footer prop",
      isOpen:false,
      isOpen2:false
    }
  },
  methods:{
    handleClick(){
      console.log(this.$refs.name);
      const name=this.$refs.name;
      name.classList.add("active");
    },
    toggleModal(){
      this.isOpen=!this.isOpen
    },
    toggleModal2(){
      this.isOpen2=!this.isOpen2
    }
  },
  name: 'App',
  components: {
    HelloWorld,
    Modal
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
h1{
  color:seagreen;
}
</style>
