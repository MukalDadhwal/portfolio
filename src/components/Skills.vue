<template>
  <section id="skills" class="skills-section">
    <h2 class="section-title">// Skills</h2>
    <div class="skills-container">
      <div v-for="(skill, index) in skills" :key="skill.name" class="skill-tag"
        :style="{ animationDelay: `${index * 100}ms` }">
        &lt;<i :class="skill.icon"></i>
        <span>{{ skill.name }}</span> /&gt;
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Skills',
  data() {
    return {
      skills: [
        { name: 'Java', icon: 'devicon-java-plain' },
        { name: 'Go', icon: 'devicon-go-plain' },
        { name: 'Python', icon: 'devicon-python-plain' },
        { name: 'Dart', icon: 'devicon-dart-plain' },
        { name: 'C', icon: 'devicon-c-plain' },
        { name: 'Flutter', icon: 'devicon-flutter-plain' },
        { name: 'Vue.js', icon: 'devicon-vuejs-plain' },
        { name: 'Express.js', icon: 'devicon-express-original' },
        { name: 'Docker', icon: 'devicon-docker-plain' },
        { name: 'Git', icon: 'devicon-git-plain' },
        { name: 'GitHub Actions', icon: 'devicon-github-original' },
        { name: 'PostgreSQL', icon: 'devicon-postgresql-plain' },
        { name: 'MySQL', icon: 'devicon-mysql-plain' },
        { name: 'Postman', icon: 'devicon-postman-plain' },
        { name: 'Android Studio', icon: 'devicon-androidstudio-plain' },
        { name: 'GCP', icon: 'devicon-googlecloud-plain' },
        { name: 'Firebase', icon: 'devicon-firebase-plain' },
        { name: 'MongoDB', icon: 'devicon-mongodb-plain' },
        { name: 'Arduino', icon: 'devicon-arduino-plain' },
        { name: 'Linux', icon: 'devicon-linux-plain' }
      ],
    };
  },
};
</script>

<style scoped>
.skills-section {
  padding: 4rem 2rem;
}

.section-title {
  font-family: var(--header-font);
  font-size: 2rem;
  color: var(--accent-green);
  margin-bottom: 3rem;
  text-align: center;
}

.skills-container {
  display: flex;
  flex-wrap: wrap;
  justify-content: center;
  gap: 1rem;
  max-width: 960px;
  margin: 0 auto;
}

.skill-tag {
  background-color: #161b22;
  border: 1px solid #30363d;
  color: var(--accent-blue);
  font-family: var(--header-font);
  font-size: 1.2rem;
  padding: 0.5rem 1rem;
  border-radius: 4px;
  opacity: 0;
  transform: translateY(20px);
  animation: slideUpFadeIn 0.5s forwards;
}

.skill-tag i {
  margin-right: 0.5rem;
  vertical-align: middle;
}

.skill-tag span {
  vertical-align: middle;
}

@keyframes slideUpFadeIn {
  to {
    opacity: 1;
    transform: translateY(0);
  }
}
</style>
