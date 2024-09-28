<script lang="ts">
  interface Page {
    title: string;
    path: string;
    screenshot: string;
  }

  const pages: Page[] = [
    { title: "Page 1", path: "/page1", screenshot: "https://placehold.co/120x120" },
    { title: "Page 2", path: "/page2", screenshot: "https://placehold.co/120x120" },
    // Add more pages as needed
  ];
</script>

<main>
  <div class="page-list">
    {#each pages as page}
      <a href={page.path} class="page-link">
        <img src={page.screenshot} alt={`Screenshot of ${page.title}`} />
        <h2>{page.title}</h2>
      </a>
    {/each}
  </div>
</main>

<style>
  .page-list {
    display: flex;
    flex-direction: column;
    gap: 1rem;
  }

  .page-link {
    display: flex;
    align-items: center;
    text-decoration: none;
    color: inherit;
    padding: 1rem;
    transition: background-color 0.2s ease-in-out;
  }

  .page-link:hover {
    background-color: #f0f0f0;
  }

  img {
    width: 100px;
    height: auto;
    border-radius: 4px;
    margin-right: 1rem;
  }

  h2 {
    margin: 0;
  }
</style>