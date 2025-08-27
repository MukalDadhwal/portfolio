<template>
  <div id="app">
    <Navbar />
    <main>
      <Home />
      <About />
      <Skills />
      <Projects />
      <Contact />
    </main>
  </div>
</template>

<script>
import Navbar from './components/Navbar.vue'
import Home from './components/Home.vue'
import About from './components/About.vue'
import Skills from './components/Skills.vue'
import Projects from './components/Projects.vue'
import Contact from './components/Contact.vue'

export default {
  name: 'App',
  components: {
    Navbar,
    Home,
    About,
    Skills,
    Projects,
    Contact
  },
  mounted() {
    const observer = new IntersectionObserver((entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          entry.target.classList.add('is-visible');
        }
      });
    }, {
      threshold: 0.1
    });

    document.querySelectorAll('section').forEach(section => {
      observer.observe(section);
    });
  }
}
</script>

<style>
section {
  opacity: 0;
  transform: translateY(20px);
  transition: opacity 0.6s ease-out, transform 0.6s ease-out;
}

section.is-visible {
  opacity: 1;
  transform: translateY(0);
}
</style>
