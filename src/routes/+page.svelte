<script>
  import { projects } from '$lib/projects.js';
</script>

<svelte:head>
  <title>Ashwyn – Portfolio</title>
</svelte:head>

<header>
  <div class="hero">
    <h1>Ashwyn</h1>
    <p class="tagline">Software developer building things worth building.</p>
    <nav>
      <a href="https://github.com/Ashwyn28" target="_blank" rel="noopener">GitHub</a>
    </nav>
  </div>
</header>

<main>
  <section class="projects">
    <h2>Projects</h2>
    <div class="grid">
      {#each projects as project}
        <article class="card">
          <h3>{project.title}</h3>
          <p>{project.description}</p>
          <ul class="tags">
            {#each project.tags as tag}
              <li>{tag}</li>
            {/each}
          </ul>
          <div class="links">
            {#if project.repo}
              <a href={project.repo} target="_blank" rel="noopener">Source</a>
            {/if}
            {#if project.demo}
              <a href={project.demo} target="_blank" rel="noopener">Live</a>
            {/if}
          </div>
        </article>
      {/each}
    </div>
  </section>
</main>

<footer>
  <p>Built with SvelteKit · <a href="https://github.com/Ashwyn28" target="_blank" rel="noopener">Ashwyn28</a></p>
</footer>

<style>
  :global(*, *::before, *::after) {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }

  :global(body) {
    font-family: 'Segoe UI', system-ui, sans-serif;
    background: #0d1117;
    color: #e6edf3;
    line-height: 1.6;
  }

  :global(a) {
    color: #58a6ff;
    text-decoration: none;
  }

  :global(a:hover) {
    text-decoration: underline;
  }

  /* Hero */
  header {
    border-bottom: 1px solid #21262d;
  }

  .hero {
    max-width: 900px;
    margin: 0 auto;
    padding: 5rem 1.5rem 4rem;
  }

  h1 {
    font-size: clamp(2.5rem, 6vw, 4rem);
    font-weight: 700;
    letter-spacing: -0.02em;
    background: linear-gradient(135deg, #e6edf3 0%, #8b949e 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .tagline {
    margin-top: 0.75rem;
    font-size: 1.15rem;
    color: #8b949e;
  }

  nav {
    margin-top: 1.5rem;
    display: flex;
    gap: 1rem;
  }

  nav a {
    display: inline-flex;
    align-items: center;
    gap: 0.4rem;
    padding: 0.45rem 1rem;
    border: 1px solid #30363d;
    border-radius: 6px;
    font-size: 0.9rem;
    color: #e6edf3;
    transition: border-color 0.15s, background 0.15s;
  }

  nav a:hover {
    border-color: #58a6ff;
    background: rgba(88, 166, 255, 0.08);
    text-decoration: none;
  }

  /* Projects */
  main {
    max-width: 900px;
    margin: 0 auto;
    padding: 3rem 1.5rem;
  }

  h2 {
    font-size: 1.4rem;
    font-weight: 600;
    color: #e6edf3;
    margin-bottom: 1.5rem;
    padding-bottom: 0.5rem;
    border-bottom: 1px solid #21262d;
  }

  .grid {
    display: grid;
    grid-template-columns: repeat(auto-fill, minmax(280px, 1fr));
    gap: 1rem;
  }

  .card {
    background: #161b22;
    border: 1px solid #30363d;
    border-radius: 10px;
    padding: 1.25rem 1.5rem;
    display: flex;
    flex-direction: column;
    gap: 0.75rem;
    transition: border-color 0.15s, transform 0.15s;
  }

  .card:hover {
    border-color: #58a6ff;
    transform: translateY(-2px);
  }

  .card h3 {
    font-size: 1rem;
    font-weight: 600;
    color: #e6edf3;
  }

  .card p {
    font-size: 0.875rem;
    color: #8b949e;
    flex: 1;
  }

  .tags {
    display: flex;
    flex-wrap: wrap;
    gap: 0.4rem;
    list-style: none;
  }

  .tags li {
    font-size: 0.75rem;
    padding: 0.2rem 0.6rem;
    border-radius: 20px;
    background: rgba(88, 166, 255, 0.1);
    color: #58a6ff;
    border: 1px solid rgba(88, 166, 255, 0.2);
  }

  .links {
    display: flex;
    gap: 0.75rem;
    font-size: 0.85rem;
  }

  .links a {
    color: #8b949e;
    transition: color 0.15s;
  }

  .links a:hover {
    color: #e6edf3;
    text-decoration: none;
  }

  /* Footer */
  footer {
    text-align: center;
    padding: 2rem 1.5rem;
    border-top: 1px solid #21262d;
    font-size: 0.85rem;
    color: #484f58;
  }
</style>
