<template>
    <header class="header">
        <div class="">
            <h1>Logo</h1>
        </div>
        <span class="menu-toggle" v-on:click="toggleMenu"> {{ menuOpen ? 'X':'+' }} </span>
        <nav class="nav" v-bind:class="{active:menuOpen}">
            <ul>
                <li> <RouterLink to="/"> Home </RouterLink> </li>
                <li> <RouterLink to="/about"> About </RouterLink> </li>
            </ul>
        </nav>
    </header>
</template>
<script>
import { RouterLink } from 'vue-router';

export default {
    name: "HeaderComponent",
    components: { RouterLink },
    data(){
        return{
            menuOpen:false
        }
    },
    methods:{
        toggleMenu(){
            this.menuOpen = !this.menuOpen
            console.log("hello")
        }
    }
}
</script>
