<template>
  <section id="about" class="about-section">
    <h2 class="section-title">// About Me</h2>
    <div class="about-content">
      <div class="about-text">
        <p v-for="(line, index) in animatedText" :key="index" class="line-by-line"
          :style="{ animationDelay: `${index * 0.2}s` }">
          {{ line }}
        </p>
      </div>
      <div class="about-image">
        <div class="image-placeholder">
          <img src="/me.jpg" alt="Mukal Dadhwal" />
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'About',
  data() {
    return {
      textLines: [
        "A passionate and driven Computer Science student with hands-on experience in backend engineering and mobile app development.",
        "From building scalable AdTech systems to developing Smart Home IoT applications, I thrive on solving complex problems.",
        "My project work, including an award-winning AI/ML platform for protein analysis, showcases my commitment to leveraging technology for impactful solutions.",
        "I am a quick learner, a team leader, and always eager to take on new challenges."
      ],
      animatedText: [],
    };
  },
  mounted() {
    this.animateText();
  },
  methods: {
    animateText() {
      this.textLines.forEach((line, index) => {
        setTimeout(() => {
          this.animatedText.push(line);
        }, index * 300); // Stagger the animation of each line
      });
    },
  },
};
</script>

<style scoped>
.about-section {
  padding: 4rem 2rem;
}

.section-title {
  font-family: var(--header-font);
  font-size: 2rem;
  color: var(--accent-green);
  margin-bottom: 3rem;
  text-align: center;
}

.about-content {
  display: grid;
  grid-template-columns: 3fr 1fr;
  gap: 3rem;
  align-items: center;
  max-width: 960px;
  margin: 0 auto;
}

.about-text {
  font-family: var(--body-font);
  font-size: 1.1rem;
  color: var(--text-color);
}

.line-by-line {
  opacity: 0;
  transform: translateX(-20px);
  animation: slideInFadeIn 0.5s forwards;
  margin-bottom: 1rem;
}

@keyframes slideInFadeIn {
  to {
    opacity: 1;
    transform: translateX(0);
  }
}

.about-image .image-placeholder {
  width: 200px;
  height: 200px;
  border-radius: 50%;
  position: relative;
  display: flex;
  justify-content: center;
  align-items: center;
  animation: neon-glow 2s infinite alternate;
}

.about-image img {
  width: 100%;
  height: 100%;
  border-radius: 50%;
  object-fit: cover;
  border: 3px solid var(--accent-blue);
}

@keyframes neon-glow {
  from {
    box-shadow: 0 0 10px var(--accent-blue), 0 0 20px var(--accent-blue), 0 0 30px var(--accent-blue);
  }

  to {
    box-shadow: 0 0 20px var(--accent-blue), 0 0 30px var(--accent-purple), 0 0 40px var(--accent-purple);
  }
}
</style>
