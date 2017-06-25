<template>
  <div class="hello">
    <Sidebar></Sidebar>
    <Search v-if='page'></Search>
    <Favorites v-else></Favorites>
  </div>
</template>

<script>
import Sidebar from './Sidebar';
import Search from './Search';
import Favorites from './Favorites';

export default {
  name: 'hello',
  data() {
    return {
      page: true,
    };
  },
  components: {
    Sidebar,
    Search,
    Favorites,
  },
  // events: {
  //   toggle: () => {
  //     this.page = !this.page;
  //   },
  // },
  // props: ['page'],
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style>
body {
  font-family: "Courier New", Courier, "Lucida Sans Typewriter", "Lucida Typewriter", monospace;
}
.inputBar {
  width: 450px;
  height: 50px;
  border-radius: 75px;
  text-shadow: none;
  border: 1.5px solid #ccc;
  padding-left: 35px;
}
.contentText {
  padding-left: 35px;
  text-align:left;
  font-size: 30px;
}
.inputBar:focus {
  outline:none; 
}
.sidebar {
  position: fixed;
  top: 0;
  left: 0;
  display: inline;
  /*display: flex;
  justify-content: flex-start;*/
}
.logoText {
  position: absolute;
  right: 40px;
  top: 35px;
}
.menuText {
  position: absolute;
  right: 0px;
  top: 350px;
  cursor: pointer;
}
.menuItem {
  color: white;
  padding-right: 45px;
  padding-left: 18px;
  display: flex;
  justify-content: flex-start;
}
.background {
  background-color: rgba(255,255,255,0.4)
}
.content {
  position: fixed;
  top: 100px;
  left: 600px;
}


</style>
