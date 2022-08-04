<script>
  const NavBarEls = ['Projects', 'About'];
</script>

<nav>
  <ul class="flex m-top">
    {#each NavBarEls as el}
      <li class="mx-4">{el}</li>
    {/each}
  </ul>
</nav>
