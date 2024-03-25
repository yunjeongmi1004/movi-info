<template>
  <Navbar />
  <Event :text="text" />
  <SearchBar :data="data"/>
  <Movies 
    :dataitem="dataitem" 
    @openModal = "isModal = true; selectedMovie = $event"
    @increslike = "increslike($event)"/>
  <Modal 
      :dataitem="dataitem" 
      :isModal="isModal" 
      :selectedMovie="selectedMovie" 
      @closeModal = "isModal = false" 
    />

</template>

<script>
// import { dataitem } from './assets/movis';
import  dataitem  from './assets/movis';
import Navbar from './components/Navbar.vue';
import Movies from './components/Movies.vue';
import Event from './components/Event.vue';
import Modal from './components/Modal.vue';
import SearchBar from './components/SearchBar.vue';
console.log(dataitem);

export default{
  name:'App',
  // dataitem,
  data(){
    return{
      isModal :false,
      dataitem : dataitem,
      selectedMovie : 0,
      text:"넷플릭스",
    }
  },
  methods:{
    increslike(i){
      this.dataitem[i].like += 1;
    }
  },
  components:{
    Navbar : Navbar,
    Event : Event,
    Modal : Modal,
    Movies : Movies,
    SearchBar,
  }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
}

body {
  max-width: 768px;
  margin: 0 auto;
  padding: 20px;
}

h1,
h2,
h3 {
  margin-bottom: 1rem;
}

p {
  margin-bottom: 0.5rem;
}

button {
  margin-right: 10px;
  margin-top: 1rem;
}

.item {
  width: 100%;
  border: 1px solid #ccc;
  display: flex;
  margin-bottom: 20px;
  padding: 1rem;
}

.item figure {
  width: 30%;
  margin-right: 1rem;
}

.item img {
  width: 100%;
}

.item .info {
  width: 100%;
}

.modal {
  background: rgba(0, 0, 0, 0.2);
  position: fixed;
  left: 0;
  top: 0;
  width: 100%;
  height: 100vh;
  display: flex;
  justify-content: center;
  align-items: center;
}

.modal .inner {
  background: #fff;
  width: 80%;
  padding: 20px;
  border-radius: 10px;
}
</style>