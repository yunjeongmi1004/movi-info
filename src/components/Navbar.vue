<template>
   <nav class="navbar">
        <a href="#">Home</a>
        <a href="#">Movies</a>
        <a href="#">About</a>
   </nav>
</template>
<script>
export default{
    name : 'NavbarComponent',
}
</script>
<style>
.navbar{
    background:#eee;
    padding:20px;
}
.navbar a{
    color:#444;
    text-align: center;
}
</style>