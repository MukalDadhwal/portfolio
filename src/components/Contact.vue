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
         <div class="info-line">
            <span class="variable">const </span>
            <span class="name">email</span>
            =
            <a href="mailto:mukaldadhwal@gmail.com" class="string">
              'mukaldadhwal@gmail.com'
            </a>;
          </div>
         <div class="info-line">
            <span class="variable">const </span>
            <span class="name">linkedin</span>
            =
            <a href="https://www.linkedin.com/in/mukal-dadhwal/" target="_blank" class="string">
              'LinkedIn'
            </a>;
          </div>
          <div class="info-line">
            <span class="variable">const </span>
            <span class="name">x</span>
            =
            <a href="https://x.com/mukaldadhwal" target="_blank" class="string">
              'X (Twitter)'
            </a>;
          </div>
          <div class="info-line">
            <span class="variable">const </span>
            <span class="name">leetcode</span>
            =
            <a href="https://leetcode.com/u/Mkk8/" target="_blank" class="string">
              'LeetCode'
            </a>;
          </div>
          <div class="info-line">
            <span class="variable">const </span>
            <span class="name">github</span>
            =
            <a href="https://github.com/MukalDadhwal/" target="_blank" class="string">
              'GitHub'
            </a>;
          </div>
        </div>
        <div class="resume-section">
          <a href="/Mukal_Resume.pdf" download="Mukal_Dadhwal_Resume.pdf" class="resume-button">
            Download Resume
          </a>
       </div>
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
  display: flex;
    justify-content: center;
    max-width: 960px;
  margin: 0 auto;
}

.contact-content {
  background-color: #161b22;
  border: 1px solid #30363d;
  border-radius: 8px;
  padding: 2rem 2.5rem;
  text-align: left;
  font-family: var(--header-font);
  width: 100%;
  max-width: 860px;
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
  white-space: nowrap;
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
  margin-top: 2rem;
  text-align: center;
}

.resume-button {
  background-color: var(--accent-green);
  color: var(--bg-color);
  font-family: var(--header-font);
  font-size: 1.1rem;
    padding: 0.8rem 1.75rem;
  border-radius: 4px;
  text-decoration: none;
  transition: background-color 0.3s ease, transform 0.3s ease;
  display: inline-block;
  box-shadow: 0 0 0 1px rgba(0, 255, 136, 0.25);
}

.resume-button:hover {
  background-color: #2c9f5a;
  transform: translateY(-2px);
}

/* Mobile Responsive Styles */
@media (max-width: 768px) {
  .contact-section {
    padding: 2rem 1rem;
  }

  .section-title {
    font-size: 1.6rem;
    margin-bottom: 2rem;
  }

  .contact-wrapper {
    gap: 1.5rem;
  }

  .contact-content {
    padding: 1.5rem;
    font-size: 0.95rem;
  }

  .info-line {
    margin-bottom: 0.5rem;
      white-space: normal;
    word-break: break-all;
  }

  .resume-button {
    font-size: 1rem;
    padding: 0.7rem 1.2rem;
  }
}

@media (max-width: 480px) {
  .contact-section {
    padding: 1.5rem 0.5rem;
  }

  .section-title {
    font-size: 1.4rem;
  }

  .contact-content {
    padding: 1rem;
    font-size: 0.85rem;
  }

  .comment {
    font-size: 0.85rem;
  }

  .info-line {
    font-size: 0.8rem;
    margin-bottom: 0.6rem;
  }

  .resume-button {
    font-size: 0.9rem;
    padding: 0.6rem 1rem;
    width: 100%;
  }
}
</style>
