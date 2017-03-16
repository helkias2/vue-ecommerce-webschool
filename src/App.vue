<template>
  <div class="phone-viewport">
    <md-toolbar>
      <md-button class="md-icon button" v-on:click.native="toggleLeftSidenav">
        <md-icon>menu</md-icon>
      </md-button>

      <h1 class="md-title">{{ title }}</h1>
    </md-toolbar>

    <md-sidenav class="md-left" ref="leftSidenav">
      <md-toolbar class="md-medium">
        <div class="md-toolbar-container">
          <h2 class="md-title">Sidenav content</h2>
        </div>
      </md-toolbar>

      <md-list>
        <md-list-item>Perfil</md-list-item>
        <md-list-item>
          <router-link 
            v-on:click.native="closeLeftSidenav" 
            to="/categories">Categorias</router-link>
        </md-list-item>
        <md-list-item>
          <router-link 
            v-on:click.native="closeLeftSidenav" 
            to="/products">Produtos</router-link>
        </md-list-item>
        <md-list-item>Sair</md-list-item>
      </md-list>
    </md-sidenav>

    <md-row>
      <router-view></router-view>
    </md-row>
  </div>
</template>

<script>
  export default {
    name: 'WebschoolComponent',

    data () {
      return {
        title: 'Ecommerce Webschool'
      }
    },

    methods: {
      toggleLeftSidenav () {
        this.$refs.leftSidenav.toggle()
      },
      closeLeftSidenav () {
        this.$refs.leftSidenav.close()
      }
    }
  }
</script>

<style>
</style>
