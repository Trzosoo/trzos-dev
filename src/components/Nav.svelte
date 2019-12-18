<script>
  export let segment;
</script>

<style>
  nav {
    border-bottom: 1px solid rgba(0, 62, 255, 0.1);
  }

  li {
    display: inline-block;
  }

  .selected {
    position: relative;
    display: inline-block;
  }

  .selected::after {
    position: absolute;
    content: "";
    width: calc(100% - 1em);
    height: 2px;
    background-color: #3182ce;
    display: block;
    bottom: -1px;
  }

  a {
    text-decoration: none;
    padding: 1em 0.5em;
    display: block;
  }
</style>

<nav>
  <div class="max-w-3xl mx-auto flex justify-between">
    <ul>
      <li>
        <a
          class="font-bold hover:text-blue-700"
          class:selected={segment === undefined}
          href=".">
          Bartosz Trzos
        </a>
      </li>
    </ul>
    <ul>
      <li>
        <a
          class="hover:text-blue-700"
          class:selected={segment === 'resume'}
          href="resume">
          Resume
        </a>
      </li>

      <!-- for the blog link, we're using rel=prefetch so that Sapper prefetches
		     the blog data when we hover over the link or tap it on a touchscreen -->
      <li>
        <a
          rel="prefetch"
          class="hover:text-blue-700"
          class:selected={segment === 'blog'}
          href="blog">
          Blog
        </a>
      </li>
    </ul>
  </div>
</nav>
