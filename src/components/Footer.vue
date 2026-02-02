<template>
  <footer class="site-footer">
    <div class="footer-inner">
      <div class="footer-meta">
        <p class="footer-title">&lt;/&gt; Built with care</p>
        <p class="footer-text">
          © {{ currentYear }} Mukal Dadhwal · Crafted with Vue 3 &amp; Vite
        </p>
      </div>
      <div class="footer-quote">
        <p class="quote-text">
          “Programs must be written for people to read, and only incidentally for machines to execute.”
        </p>
        <p class="quote-author">— Harold Abelson</p>
      </div>
    </div>
  </footer>
</template>

<script>
export default {
  name: 'Footer',
  computed: {
    currentYear() {
      return new Date().getFullYear();
    }
  }
}
</script>

<style scoped>
.site-footer {
  border-top: 1px solid rgba(0, 255, 136, 0.2);
  padding: 1.5rem 2rem 2rem;
  background: radial-gradient(circle at top, rgba(0, 255, 136, 0.08), transparent 55%);
}

.footer-inner {
  max-width: 960px;
  margin: 0 auto;
  display: flex;
  flex-wrap: wrap;
  justify-content: space-between;
  align-items: flex-start;
  gap: 1.5rem;
  font-family: var(--body-font);
}

.footer-meta {
  flex: 1 1 220px;
}

.footer-title {
  color: var(--accent-green);
  font-weight: 700;
  margin-bottom: 0.25rem;
}

.footer-text {
  color: var(--text-color);
  font-size: 0.9rem;
}

.footer-quote {
  flex: 2 1 260px;
  font-size: 0.9rem;
  color: #8b949e;
}

.quote-text {
  font-style: italic;
  margin-bottom: 0.25rem;
}

.quote-author {
  color: var(--accent-blue);
}

@media (max-width: 768px) {
  .site-footer {
    padding: 1.25rem 1.25rem 1.75rem;
  }

  .footer-inner {
    flex-direction: column;
    align-items: flex-start;
  }
}

@media (max-width: 480px) {
  .site-footer {
    padding: 1rem 0.75rem 1.5rem;
  }

  .footer-text,
  .footer-quote {
    font-size: 0.8rem;
  }
}
</style>

