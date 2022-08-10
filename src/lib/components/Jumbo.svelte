<script>
  let visible = false;
  function typewriter(node, { speed = 1 }) {
    const valid =
      node.childNodes.length === 1 &&
      node.childNodes[0].nodeType === Node.TEXT_NODE;
    if (!valid) {
      throw new Error(
        `This transition only works on elements with a single text node child`
      );
    }
    const text = node.textContent;
    const duration = text.length / (speed * 0.01);
    return {
      duration,
      tick: (t) => {
        const i = Math.trunc(text.length * t);
        node.textContent = text.slice(0, i);
      },
    };
  }
</script>

<header>
  <label>
    <input type="checkbox" bind:checked={visible} />
    visible
  </label>
  {#if visible}
    <p transition:typewriter>The quick brown fox jumps over the lazy dog</p>
  {/if}
  <div
    class="p-12 text-center relative overflow-hidden bg-no-repeat bg-cover h-96 lg:h-screen"
    style="background-image: url('https://mdbootstrap.com/img/Photos/Inne/ostia.jpg')"
  >
    <div
      class="absolute top-0 right-0 bottom-0 left-0 w-full h-full overflow-hidden bg-fixed"
      style="background-color: rgba(2, 56, 53, 0.7)"
    >
      <div class="flex justify-center items-center h-full">
        <div class="text-white">
          {#if visible}
            <h2 transition:typewriter class="font-semibold text-4xl mb-4">
              Ronald Vilorio
            </h2>
            <h4 transition:typewriter class="font-semibold text-xl mb-6">
              Developer, Problem Solver, Runner
            </h4>
          {/if}
        </div>
      </div>
    </div>
  </div>
</header>
