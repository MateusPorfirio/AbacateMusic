<template>
    <div class="navbar">
        <img class="logo" src="../assets/logo-abacate.png">
        <input type="text" class="search" placeholder="Pesquise por música, artista ou albúm...">
    </div>
</template>

<script>
export default {
    name: 'Navbar'
}
</script>

<style>
    .navbar {
        height: 80px;
        width: 100%;
        background-color:#091012;
        display: flex;
        align-content: center;
        align-items: center; 
    }

    .logo {
        float: left;
        margin-left: 50px;
        width: 150px;
    }

    .search {
        height: 40px;
        width: 600px;
        background-color: #151A1C;
        box-shadow: 4px 0px 15px 3px #000000;
        border-radius: 30px;
        margin-left: 30px;
        outline: none;
        border: none;
        padding-left: 20px;
        color: #fff;
    }
</style>