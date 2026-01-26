<template>
  <nav>
    <button 
      class="menu-toggle" 
      @click="toggleMenu" 
      :aria-label="menuOpen ? 'Close menu' : 'Open menu'"
      :aria-expanded="menuOpen"
    >
      <span class="hamburger" :class="{ 'is-active': menuOpen }"></span>
    </button>
    <ul :class="{ 'is-open': menuOpen }">
      <li><a href="#home" @click="closeMenu">Home</a></li>
      <li><a href="#about" @click="closeMenu">About</a></li>
      <li><a href="#skills" @click="closeMenu">Skills</a></li>
      <li><a href="#projects" @click="closeMenu">Projects</a></li>
      <li><a href="#contact" @click="closeMenu">Contact</a></li>
    </ul>
  </nav>
</template>

<script>
export default {
  name: 'Navbar',
  data() {
    return {
      menuOpen: false
    }
  },
  methods: {
    toggleMenu() {
      this.menuOpen = !this.menuOpen
    },
    closeMenu() {
      this.menuOpen = false
    }
  }
}
</script>

<style scoped>
.menu-toggle {
  display: none;
  background: none;
  border: none;
  cursor: pointer;
  padding: 0;
  z-index: 1001;
}

.hamburger {
  display: block;
  width: 30px;
  height: 2px;
  background-color: var(--accent-green);
  position: relative;
  transition: background-color 0.3s ease;
}

.hamburger::before,
.hamburger::after {
  content: '';
  position: absolute;
  width: 30px;
  height: 2px;
  background-color: var(--accent-green);
  transition: transform 0.3s ease;
}

.hamburger::before {
  top: -8px;
}

.hamburger::after {
  top: 8px;
}

.hamburger.is-active {
  background-color: transparent;
}

.hamburger.is-active::before {
  transform: rotate(45deg) translate(6px, 6px);
}

.hamburger.is-active::after {
  transform: rotate(-45deg) translate(6px, -6px);
}

@media (max-width: 768px) {
  .menu-toggle {
    display: block;
    position: fixed;
    top: 1.5rem;
    right: 2rem;
  }

  nav ul {
    position: fixed;
    top: 0;
    right: 0;
    height: 100vh;
    width: 70%;
    max-width: 300px;
    background-color: rgba(13, 17, 23, 0.98);
    backdrop-filter: blur(10px);
    flex-direction: column;
    justify-content: center;
    align-items: center;
    gap: 2rem;
    transform: translateX(100%);
    transition: transform 0.3s ease;
    border-left: 1px solid rgba(0, 255, 136, 0.2);
  }

  nav ul.is-open {
    transform: translateX(0);
  }

  nav ul li a {
    font-size: 1.2rem;
  }
}
</style>
