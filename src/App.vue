<template>
  <div class="pwa-layout-transparent mdl-layout mdl-js-layout mdl-layout--fixed-header">
    <header class="mdl-layout__header mdl-layout__header--transparent">
      <div class="mdl-layout__header-row">
        <span class="mdl-layout-title">Coffee</span>
      </div>
    </header>
    <div class="mdl-layout__drawer">
      <span class="mdl-layout-title">Coffee</span>
      <nav class="mdl-navigation">
        <router-link class="mdl-navigation__link" to="/" @click.native="hideMenu">Home</router-link>
        <router-link class="mdl-navigation__link" to="/post" @click.native="hideMenu">About</router-link>
      </nav>
    </div>
    <main class="mdl-layout__content">
      <div class="page-content">
        <router-view></router-view>
      </div>
    </main>
  </div>
</template>

<script>
  require('material-design-lite')
  export default {
    name: 'app'
  }
</script>

<style>
  @import url('https://fonts.googleapis.com/icon?family=Material+Icons');
  @import url('https://code.getmdl.io/1.3.0/material.indigo-red.min.css');
  @import url('https://maps.googleapis.com/maps/api/js?key=YOUR_API_KEY&libraries=places');
  html {
    background-color: rgba(0, 0, 0, 0.719);
  }
  .pwa-layout-transparent {
    background: url('./assets/background.jpeg') center/cover ;
    opacity: 0.6;
  }
  .pwa-layout-transparent .mdl-layout__header,
  .pwa-layout-transparent .mdl-layout__drawer-button {
    color: rgb(255, 255, 255);
  }
</style>
