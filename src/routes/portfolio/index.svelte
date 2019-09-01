<script context="module">
  export function preload({ params, query }) {
    return this.fetch(`blog.json`)
      .then(r => r.json())
      .then(projects => {
        return { projects };
      });
  }
</script>

<script>
  export let projects;
</script>

<style>
  .projects {
    margin: auto;
    max-width: 1200px;
  }
  .projects .center {
    text-align: center;
  }
  .project-single {
    margin: 1rem;
    position: relative;
  }
  .project-image {
    display: block;
    width: 100%;
    max-width: 100%;
    height: auto;
  }
  .project {
    margin-bottom: 50px;
  }
  .overlay h2 {
    color: var(--white);
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    -ms-transform: translate(-50%, -50%);
  }
  .overlay {
    background-color: var(--dark-grey);
    height: 100%;
    left: 0;
    top: 0;
    right: 0;
    position: absolute;
    width: 100%;
    opacity: 0;
    transition: 0.5s ease;
  }
  .overlay:hover .overlay {
    opacity: 1;
  }
</style>

<svelte:head>
  <title>Blog</title>
</svelte:head>

<h1 class="title">Coming Soon!</h1>

<!-- <ul> -->
<!-- {#each projects as project} -->
<!-- we're using the non-standard `rel=prefetch` attribute to
				tell Sapper to load the data for the page as soon as
				the user hovers over the link or taps it, instead of
				waiting for the 'click' event -->
<!-- <li>
      <a rel="prefetch" href="portfolio/{project.slug}">{project.title}</a>
    </li> -->
<!-- {/each} -->
<!-- </ul> -->
