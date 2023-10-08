<script>
  import "../app.css";
  import Header from '../components/Header.svelte';
  import Footer from '../components/Footer.svelte';

  let scrollY = 0;
  let innerHeight = 0;
  let innerWidth = 0;

  function goTop() {
    window.scrollTo({
      top: 0,
      behavior: "smooth",
    });
  }

</script>

<div class="relative flex flex-col max-w-[1400px] mx-auto w-full text-sm sm:text-base min-h-screen">
  <div class="">
    <button>
      <i class="fa-solid fa-arrow-up" on:click={goTop}
      ></i>
    </button>
  </div>

  <Header />

  <slot />

  <Footer />
</div>

<svelte:window bind:scrollY={scrollY} bind:innerHeight bind:innerWidth />