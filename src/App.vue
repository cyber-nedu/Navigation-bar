<template>
  <div
    id="app"
    class="min-h-screen bg-[var(--nav-bg)] text-[var(--nav-text)] transition-colors duration-300"
  >
    <Navbar />
    <PageContent />
    <Footer />
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue';
import PageContent from './components/PageContent.vue';
import Footer from './components/Footer.vue';

export default {
  name: 'App',
  components: {
    Navbar,
    PageContent,
    Footer,
  },
};
</script>