<template>
  <section id="projects" class="projects-section">
    <h2 class="section-title">// Projects</h2>
    <div class="projects-grid">
      <div class="project-card" v-for="project in projects" :key="project.title">
        <div class="card-content">
          <h3 class="project-title">{{ project.title }}</h3>
          <p class="project-description">{{ project.description }}</p>
        </div>
        <a :href="project.github" target="_blank" class="view-code-btn">View Code</a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Projects',
  data() {
    return {
      projects: [
        {
          title: 'Krishi Gyan — Smart Farming Solution',
          description: 'A mobile app for farmers providing personalized crop recommendations based on real-time soil monitoring via Arduino-based sensors.',
          github: 'https://github.com/Krishi-Gyan/Krishi-Gyan-App',
        },
        {
          title: 'Proteios — Protein Anomaly Detection',
          description: 'An AI/ML platform to detect anomalous proteins using VAEs and LLMs. Ranked top 105 nationally in the Google Solution Challenge 2025.',
          github: 'https://github.com/MukalDadhwal/proteios',
        },
        {
          title: 'Gauseva App — Stray Cattle Reporting',
          description: 'A mobile platform for reporting stray cattle using geotagged images, routing them to NGOs for intervention.',
          github: 'https://github.com/MukalDadhwal/Gauseva-App',
        },
        {
          title: 'Chillinq — Social Networking App',
          description: 'Redesigned the UI/UX of a cross-platform social app, improving user onboarding and app responsiveness.',
          github: 'https://github.com/chillinqapp',
        },
      ],
    };
  },
};
</script>

<style scoped>
.projects-section {
  padding: 4rem 2rem;
}

.section-title {
  font-family: var(--header-font);
  font-size: 2rem;
  color: var(--accent-green);
  margin-bottom: 3rem;
  text-align: center;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fill, minmax(300px, 1fr));
  gap: 2rem;
  max-width: 960px;
  margin: 0 auto;
}

.project-card {
  background-color: #161b22;
  border: 1px solid #30363d;
  border-radius: 8px;
  padding: 1.5rem;
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  overflow: hidden;
  position: relative;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.project-card:hover {
  transform: scale(1.05);
  box-shadow: 0 0 20px var(--accent-blue);
}

.project-card:hover .project-title {
  color: var(--accent-blue);
  text-shadow: 0 0 10px var(--accent-blue);
}

.project-card:hover .view-code-btn {
  transform: translateY(0);
}

.project-title {
  font-family: var(--header-font);
  font-size: 1.5rem;
  color: var(--accent-green);
  margin-bottom: 1rem;
  transition: color 0.3s ease, text-shadow 0.3s ease;
}

.project-description {
  font-family: var(--body-font);
  font-size: 1rem;
  color: var(--text-color);
  flex-grow: 1;
}

.view-code-btn {
  background-color: var(--accent-blue);
  color: var(--bg-color);
  font-family: var(--header-font);
  padding: 0.5rem 1rem;
  border-radius: 4px;
  text-align: center;
  text-decoration: none;
  position: absolute;
  bottom: 0;
  left: 0;
  right: 0;
  transform: translateY(100%);
  transition: transform 0.3s ease;
}
</style>
