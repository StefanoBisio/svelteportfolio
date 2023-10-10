<script>
  import "../app.css";
  import Header from "../components/Header.svelte";
  import Footer from "../components/Footer.svelte";

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

<div
  class="relative flex flex-col max-w-[1400px] mx-auto w-full text-sm sm:text-base min-h-screen"
>
  <div
    class={"fixed bottom-0 w-full duration-200 flex p-10 z-[10] " +
      (scrollY > 0
        ? "opacity-full pointer-events-auto"
        : "opacity-0 pointer-events-none")}
  >
    <button
      on:click={goTop}
      class="ml-auto rounded-full bg-slate-900 text-violet-400 px-3 sm:px-4 hover:bg-slate-800 cursor-pointer aspect-square"
    >
      <i class="fa-solid fa-arrow-up grid place-items-center" />
    </button>
  </div>

  <Header {scrollY} />

  <slot />

  <Footer />
</div>

<svelte:window bind:scrollY bind:innerHeight bind:innerWidth />
