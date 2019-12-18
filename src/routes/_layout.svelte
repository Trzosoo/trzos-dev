<script>
  import Nav from "../components/Nav.svelte";

  export let segment;
</script>

<Nav {segment} />

<main class="container max-w-3xl py-8 px-4">
  <slot />
</main>
