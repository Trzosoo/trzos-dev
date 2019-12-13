<script>
  import Nav from '../components/Nav.svelte'

  export let segment
</script>

<Nav {segment} />

<main class="container max-w-xl">
  <slot />
</main>
