<script>
  import Footer from "../components/Footer.svelte";
  import Menu from "../components/Menu.svelte";
  export let segment;
</script>

<style>
  main {
    margin-left: var(--sidebar-width);
    padding: 5rem 2rem 5rem 0;
    width: auto;
  }

  @media only screen and (max-width: 768px) {
    main {
      padding: 5rem 1.5rem;
      margin: 0;
    }
  }
</style>

<Menu {segment} />

<main>
  <slot />
</main>

<Footer />
