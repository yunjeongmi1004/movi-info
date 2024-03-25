<template>

<div class="container">
    <h1>MOVIINFO</h1>

    <div v-for="(item, i) in dataitem" :key="i" class="item">
    <figure>
        <img :src="`${item.imgUrl}`" :alt="item.title" />
    </figure>
    <div class="info">
        <h2 :style="textRed">{{ item.title }}</h2>
        <p>개봉 : {{ item.year }}</p>
        <p>장르 : {{ item.category }}</p>
        <button @:click="$emit('increslike', i)">좋아요</button><span>{{ item.like }}</span>
        <p>
        <button @:click="$emit('openModal', i)">상세보기</button>
        </p>
    </div>
    </div>
</div>
</template>
<script>
export default {
    name : "MoviesComponent",
    props:{
        dataitem : Array
    }
}
</script>
<style>
    .container{padding:50px}
</style>