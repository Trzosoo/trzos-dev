<script context="module">
  export function preload({ params, query }) {
    return this.fetch(`https://dev.to/api/articles/?username=remotelydev`)
      .then(r => r.json())
      .then(posts => {
        return { posts };
      });
  }
</script>

<script>
  export let posts;
</script>

<svelte:head>
  <title>Bartosz Trzos - Blog</title>
  <meta
    mame="description"
    content="Welcome to my blog. I write here about my software developement
    learning process." />
  <meta name="twitter:title" content="Bartosz Trzos - Blog" />
  <meta
    mame="twitter:description"
    content="Welcome to my blog. I write here about my software developement
    learning process." />
</svelte:head>

<ul>
  {#each posts as post}
    <!-- we're using the non-standard `rel=prefetch` attribute to
				tell Sapper to load the data for the page as soon as
				the user hovers over the link or taps it, instead of
				waiting for the 'click' event -->
    <li>
      <a rel="prefetch" href="blog/{post.slug}?id={post.id}">
        <h2 class="text-black">{post.title}</h2>
      </a>
    </li>
  {/each}
</ul>
