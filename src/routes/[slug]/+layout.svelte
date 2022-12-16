<script>
  export let data;
</script>

<div class="layout">
  <main>
    <slot />
  </main>
  <aside>
    <h2>More Posts</h2>
      <ul>
        {#each data.summaries as { slug, title }}
          <li><a href="/blog/{slug}">{title}</a></li>
        {/each}
      </ul>
  </aside>
</div>

<style>
  @media screen and (min-width: 640px) {
    .layout {
      display: grid;
      gap: 2em;
      grid-template-columns: 1fr 60ch;
    }
  }
</style>