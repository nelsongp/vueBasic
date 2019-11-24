<template>
    <div id="app">
        <h1>Vue Directives </h1>
        <h2>v-if</h2>
        <div class="logged-in" v-if="loggedIn">
            <p>You are logged in</p>
        </div>
        <div class="logged-out" v-else>
            <p>You are logged out please <button v-on:click="login">Login</button></p>
        </div>
        <div class="shopping-list" v-if="loggedIn">
            <h2>v-for</h2>
            <ul>
                <li v-for="(item, index) in shoppingList" :key="index">
                    {{item}}
                </li>
            </ul>
        </div>
        <div class="custom" v-if="custom">
            <h2>Custom Directives</h2>
            <div class="box" v-flee></div>
        </div>
        <span>{{data}}</span>
    </div>
</template>
<script>
import Vue from 'vue';
Vue.directive('flee', {
    inserted: function(el){
        var moveDistance= '150px';
        el.innerText = 'Catch me!';
        el.addEventListener("mouseover", ()=>{
            el.style.position = 'relative';
            if(el.style.left === moveDistance) el.style.left = '0px';
            else el.style.left = moveDistance;
            if(Math.round(Math.random())==1) el.style.top = moveDistance;
            else el.style.top = '0px';
        })
    }
});
export default {
    name: 'app',
    data(){
        return{
            loggedIn: false,
            shoppingList: [
                'Milk',
                'Toast',
                'Honey'
            ],
            custom: true
        }
    },
    methods: {
        login(){
            this.loggedIn = true;
        }
    }
}
</script>
<style>
#app {
    font-family: 'Avenir', Helvetica, Arial, sans-serif;
    -webkit-font-smoothing: antialised;
    -moz-osx-font-smoothing: grayscale;
    color: #2c3e50;
    margin-top: 60px;
    max-width: 60%;
    margin: 60px auto;
}
</style>