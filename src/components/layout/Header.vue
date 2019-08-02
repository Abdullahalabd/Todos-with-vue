<template>
    <header class="header">
        <h1>
            Todo List
            <div id="nav">
                <router-link to="/">Home</router-link> |
                <router-link to="/about">About</router-link>
            </div>
        </h1>
    </header>    
</template>

<script>
export default {
    name: "Header"
}
</script>

<style scoped>
    .header{
        background: #000;
        color: #fff;
        text-align: center;
        padding: 10px;
    }
    .header a{
        text-decoration: none;
    }
</style>
