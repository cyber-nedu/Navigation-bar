<template>

<nav>
  <div class="menu-item"><a href="#">HOME</a></div>
  <div class="menu-item"><a href="#">ABOUT</a></div>
  <Dropdown title="Services" :items="services" />
  <div class="menu-item"><a href="#">CONTACT</a></div>
</nav>
</template>

<script>
import Dropdown from './Dropdown.vue';
 export default {
  name: 'Navbar',
  components: {
    Dropdown
  },
  data() {
    return {
      services: [
        {
          tittle: 'Web Development',
          link: '#',
        },

        {
          tittle: 'Design',
          link: '#',
        },
        {
          tittle: 'Viedeo Editing',
          link: '#',
        },
      ],
    };
  },
 };
</script>

<style>
nav {
  display: flex;
  justify-content: center;
  align-items: center;
}

nav .menu-item {
  color: white;
  padding: 10px 20px;
  position: relative;
  text-align: center;
  border-bottom:3px solid transparent;
  display: flex;
  transition: 0.3s;
}

nav .menu-item a {
  color: inherit;
  text-decoration: none;
}

nav .menu-item:active,
nav .menu-item:hover {
  background: #444;
  border-bottom:3px solid #ff5858;
}
</style>