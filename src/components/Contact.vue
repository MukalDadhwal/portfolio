<template>
  <section id="contact" class="contact-section">
    <h2 class="section-title">// Contact</h2>
    <div class="contact-wrapper">
      <div class="contact-content">
        <p class="comment">/*</p>
        <p class="comment">&nbsp; * I'm currently open to new opportunities.</p>
        <p class="comment">&nbsp; * If you have a project in mind or just want to say hi, feel free to reach out.</p>
        <p class="comment">&nbsp; * My inbox is always open!</p>
        <p class="comment">&nbsp; */</p>
        <div class="contact-info">
          <div class="info-line"><span class="variable">const</span> <span class="name">email</span> = <a
              href="mailto:mukaldadhwal@gmail.com" class="string">'mukaldadhwal@gmail.com'</a>;</div>
          <div class="info-line"><span class="variable">const</span> <span class="name">linkedin</span> = <a
              href="https://www.linkedin.com/in/mukal-dadhwal/" target="_blank"
              class="string">'https://www.linkedin.com/in/mukal-dadhwal/'</a>;</div>
          <div class="info-line"><span class="variable">const</span> <span class="name">x</span> = <a
              href="https://x.com/mukaldadhwal" target="_blank" class="string">'https://x.com/mukaldadhwal'</a>;</div>
          <div class="info-line"><span class="variable">const</span> <span class="name">leetcode</span> = <a
              href="https://leetcode.com/u/Mkk8/" target="_blank" class="string">'https://leetcode.com/u/Mkk8/'</a>;
          </div>
          <div class="info-line"><span class="variable">const</span> <span class="name">github</span> = <a
              href="https://github.com/MukalDadhwal/" target="_blank"
              class="string">'https://github.com/MukalDadhwal/'</a>;</div>
        </div>
      </div>
      <div class="resume-section">
        <a href="/Mukal_Resume.pdf" download="Mukal_Dadhwal_Resume.pdf" class="resume-button">
          Download Resume
        </a>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  name: 'Contact',
};
</script>

<style scoped>
.contact-section {
  padding: 4rem 2rem;
  text-align: center;
}

.section-title {
  font-family: var(--header-font);
  font-size: 2rem;
  color: var(--accent-green);
  margin-bottom: 3rem;
}

.contact-wrapper {
  display: grid;
  grid-template-columns: 1fr;
  gap: 2rem;
  max-width: 800px;
  /* Increased max-width */
  margin: 0 auto;
}

@media (min-width: 768px) {
  .contact-wrapper {
    grid-template-columns: 1fr auto;
    align-items: center;
    gap: 4rem;
    /* Increased gap */
  }
}

.contact-content {
  background-color: #161b22;
  border: 1px solid #30363d;
  border-radius: 8px;
  padding: 2rem;
  text-align: left;
  font-family: var(--header-font);
  width: 100%;
}

.comment {
  color: #8b949e;
  /* GitHub comment color */
  font-style: italic;
}

.contact-info {
  margin-top: 1.5rem;
}

.info-line {
  margin-bottom: 0.5rem;
}

.variable {
  color: #ff7b72;
  /* GitHub keyword color */
}

.name {
  color: var(--accent-blue);
}

.string {
  color: #a5d6ff;
  /* GitHub string color */
  text-decoration: none;
}

.string:hover {
  text-decoration: underline;
  color: var(--accent-purple);
}

.resume-section {
  text-align: center;
}

.resume-button {
  background-color: var(--accent-green);
  color: var(--bg-color);
  font-family: var(--header-font);
  font-size: 1.2rem;
  padding: 0.8rem 1.5rem;
  border-radius: 4px;
  text-decoration: none;
  transition: background-color 0.3s ease, transform 0.3s ease;
  display: inline-block;
}

.resume-button:hover {
  background-color: #2c9f5a;
  transform: translateY(-2px);
}
</style>
