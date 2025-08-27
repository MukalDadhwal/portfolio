<template>
  <section id="home" class="home-section">
    <div class="intro-container">
      <div class="typing-effect">
        > {{ typedText }}<span class="cursor" :class="{ 'is-typing': isTyping }"></span>
      </div>
      <div class="roles">
        <transition-group name="fade-in-up">
          <span v-for="(role, index) in roles" :key="index" v-show="visibleRoles[index]" class="role"
            :style="{ animationDelay: `${index * 200}ms` }">{{ role }}</span>
        </transition-group>
      </div>
    </div>
    <transition name="fade-in-up">
      <a href="#about" v-if="showScrollIndicator" class="scroll-indicator">
        <span class="chevron"></span>
      </a>
    </transition>
  </section>
</template>

<script>
export default {
  name: 'Home',
  data() {
    return {
      fullText: 'Hello, I am Mukal Dadhwal',
      typedText: '',
      isTyping: true,
      roles: ['Software Engineer', '|', 'Problem Solver', '|', 'Developer'],
      visibleRoles: [false, false, false, false, false],
      showScrollIndicator: false,
      typingSpeed: 80,
      roleDelay: 150,
    };
  },
  mounted() {
    this.typeWriter();
  },
  methods: {
    typeWriter() {
      let i = 0;
      this.isTyping = true;
      const type = () => {
        if (i < this.fullText.length) {
          this.typedText += this.fullText.charAt(i);
          i++;
          setTimeout(type, this.typingSpeed);
        } else {
          this.isTyping = false;
          this.showRoles();
        }
      };
      type();
    },
    showRoles() {
      this.roles.forEach((_, index) => {
        setTimeout(() => {
          this.visibleRoles[index] = true;
        }, index * this.roleDelay);
      });
      // Show scroll indicator after roles are visible
      setTimeout(() => {
        this.showScrollIndicator = true;
      }, this.roles.length * this.roleDelay + 200);
    },
  },
};
</script>

<style scoped>
.home-section {
  display: flex;
  align-items: center;
  justify-content: center;
  min-height: 100vh;
  text-align: center;
  position: relative;
}

.intro-container {
  position: relative;
  z-index: 1;
  padding: 2rem;
  transform: translateY(-10vh);
}

.typing-effect {
  font-family: var(--header-font);
  font-size: clamp(1.8rem, 5vw, 3rem);
  color: var(--accent-green);
  margin-bottom: 1.5rem;
  display: inline-block;
  white-space: nowrap;
}

.cursor {
  display: inline-block;
  width: 12px;
  height: clamp(1.8rem, 5vw, 3rem);
  background-color: var(--accent-green);
  animation: blink 0.8s infinite;
  margin-left: 10px;
  vertical-align: middle;
}

.cursor.is-typing {
  animation: none;
}

@keyframes blink {

  0%,
  100% {
    opacity: 1;
  }

  50% {
    opacity: 0;
  }
}

.roles {
  font-family: var(--body-font);
  font-size: clamp(1rem, 3vw, 1.5rem);
  color: var(--text-color);
  margin-bottom: 2.5rem;
  height: 2rem;
  /* Reserve space to prevent layout shift */
}

.role {
  margin: 0 0.5rem;
  display: inline-block;
}

.scroll-indicator {
  position: absolute;
  bottom: 20vh;
  left: 50%;
  transform: translateX(-50%);
  z-index: 2;
}

.chevron {
  display: block;
  width: 24px;
  height: 24px;
  border-left: 2px solid var(--accent-green);
  border-bottom: 2px solid var(--accent-green);
  transform: rotate(-45deg);
  animation: bounce 2s infinite;
}

@keyframes bounce {

  0%,
  20%,
  50%,
  80%,
  100% {
    transform: translateY(0) rotate(-45deg);
  }

  40% {
    transform: translateY(-10px) rotate(-45deg);
  }

  60% {
    transform: translateY(-5px) rotate(-45deg);
  }
}

/* Animation Transitions */
.fade-in-up-enter-active,
.fade-in-up-leave-active {
  transition: opacity 0.5s ease, transform 0.5s ease;
}

.fade-in-up-enter-from,
.fade-in-up-leave-to {
  opacity: 0;
  transform: translateY(20px);
}
</style>
