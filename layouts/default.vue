<template>
  <div id="app">
  <header-slot>
      <!-- headerslot content will display here -->
  </header-slot>
  
    <b-navbar toggleable="lg" type="dark" variant="dark">
      <b-navbar-nav>
        <b-nav-item>
          <nuxt-link class="nav-link" to="/home">Home</nuxt-link>
        </b-nav-item>
        <b-nav-item>
          <nuxt-link class="nav-link" to="/erunners">Elite Runners</nuxt-link>
        </b-nav-item>
        <b-nav-item>
          <nuxt-link class="nav-link" to="/teams">Teams</nuxt-link>
        </b-nav-item>
        <b-nav-item>
          <nuxt-link class="nav-link" to="/about">About</nuxt-link>
        </b-nav-item>
      </b-navbar-nav>
    </b-navbar>

    <!--nuxt-link /-->     <!-- this is where the components will render when the links are triggered -->
     <nuxt />
  <FooterSlot>
  </FooterSlot>
   
  </div>
</template>

<script>
import HeaderSlot from '~/components/HeaderSlot.vue'
import FooterSlot from '../components/FooterSlot.vue'


export default {
  name: 'App',
  components: {
    HeaderSlot,
    FooterSlot,
    
  }
}
</script>

<!-- link to global stylesheet -->
<style scoped src="@/assets/styles/appStyle.css" />
