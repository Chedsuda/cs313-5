<template>
  <div id="app">
    <img alt="Vue logo" src="https://png.pngtree.com/png-vector/20190417/ourlarge/pngtree-esport-gaming-logo-with-red-dragon-theme-light-red-like-png-image_946291.jpg" width="200" height="200" />
    <HelloWorld msg="Vuegame Fighting"/>
    <h1>{{total}}</h1>
    
 <div class="row">
      <div class="col-12"><Button lable="Start" @cc="randomNo"  /></div>
    </div>

  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue';
import Button from "./components/Button.vue";

export default {
  name: 'App',
  components: {
    HelloWorld,
    Button,
  },
  data: function(){
    return{

    };
  },

  methods:{

  },
};
</script>

<style>
 body {
      background-image: url("https://gamelikethesea.com/wp-content/uploads/2020/04/Mortal-Kombat-bg02-1024x576.jpg");
      background-size: 110%;
    }

#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #f1933a;
  margin-top: 60px;

}
</style>
