<template>
    <div class="modal" v-if="isModal">
      <div class="inner">
        <h3>{{ dataitem[selectedMovie].title }}</h3>
        <p>{{ dataitem[selectedMovie].year }}</p>
        <p>{{ dataitem[selectedMovie].category }}</p>
        <p>{{ dataitem[selectedMovie].like }}</p>
        <!-- <button  @:click="isModal = false">닫기</button> -->
        <button  @:click="$emit('closeModal')">닫기</button>
      </div>
    </div>
</template>
<script>
export default {
    name:"ModalComponent",
    props:{
        dataitem : Array,
        isModal : Boolean,
        selectedMovie : Number,
    }
}
</script>
<style lang="">
    
</style>