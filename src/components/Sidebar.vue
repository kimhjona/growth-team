<template>
  <div class='sidebar'>
    <img src='./../assets/map.png'>
    <img src='./../assets/teachable-logo.png' class='logoText'>
    <span class='menuText' >
      <div class='menuItem' @click='toFav' v-bind:class="{ background: this.$parent.page }">
        <p>Search</p>
      </div>
      <div class='menuItem' @click='toSearch' v-bind:class="{ background: !this.$parent.page }">
        <p>Favorites</p>
      </div>
    </span>
  </div>
</template>

<script>
export default {
  name: 'Sidebar',
  data() {
    return {
    };
  },
  methods: {
    toFav() {
      this.$parent.page = true;
    },
    toSearch() {
      this.$parent.page = false;
    },
  },
};
</script>

<style>
  .sidebar {
    position: fixed;
    top: 0;
    left: 0;
    display: inline;
  }

</style>

