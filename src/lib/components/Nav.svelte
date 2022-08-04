<script>
  const NavBarEls = ['Projects', 'About'];
</script>

<nav class="m-top-4 border-solid border-2 border-black position:fixed">
  <ul class="flex ">
    {#each NavBarEls as el}
      <li class="mx-4">{el}</li>
    {/each}
  </ul>
</nav>
