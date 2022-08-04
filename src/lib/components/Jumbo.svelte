<script>
  import Particles from 'svelte-particles';
  import { loadFull } from 'tsparticles';

  let particlesUrl = 'http://foo.bar/particles.json';

  let particlesConfig = {
    particles: {
      color: {
        value: '#000',
      },
      links: {
        enable: true,
        color: '#000',
      },
      move: {
        enable: true,
      },
    },
  };

  let onParticlesLoaded = (event) => {
    const particlesContainer = event.detail.particles;

    // you can use particlesContainer to call all the Container class
    // (from the core library) methods like play, pause, refresh, start, stop
  };

  let particlesInit = async (engine) => {
    // you can use main to customize the tsParticles instance adding presets or custom shapes
    // this loads the tsparticles package bundle, it's the easiest method for getting everything ready
    // starting from v2 you can add only the features you need reducing the bundle size
    await loadFull(engine);
  };
</script>

<header>
  <Particles
    id="tsparticles"
    options={particlesConfig}
    on:particlesLoaded={onParticlesLoaded}
    {particlesInit}
  />
  <!-- <div
    class="p-12 text-center relative overflow-hidden bg-no-repeat bg-cover h-96 lg:h-screen"
    style="background-image: url('https://mdbootstrap.com/img/Photos/Inne/ostia.jpg')"
  >
    <div
      class="absolute top-0 right-0 bottom-0 left-0 w-full h-full overflow-hidden bg-fixed"
      style="background-color: rgba(2, 56, 53, 0.7)"
    >
      <div class="flex justify-center items-center h-full">
        <div class="text-white">
          <h2 class="font-semibold text-4xl mb-4">
            The background photo shows Lido di Ostia
          </h2>
          <h4 class="font-semibold text-xl mb-6">
            It is a coastal town in Italy that is part of Rome
          </h4>
          <a
            class="inline-block px-7 py-3 mb-1 border-2 border-gray-200 text-gray-200 font-medium text-sm leading-snug uppercase rounded hover:bg-black hover:bg-opacity-5 focus:outline-none focus:ring-0 transition duration-150 ease-in-out"
            href="#!"
            role="button"
            data-mdb-ripple="true"
            data-mdb-ripple-color="light">Learn more about Rome</a
          >
        </div>
      </div>
    </div>
  </div> -->
</header>
