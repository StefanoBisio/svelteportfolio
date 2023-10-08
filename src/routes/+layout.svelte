<script>
  import "../app.css";
  import Header from '../components/Header.svelte';
  import Footer from '../components/Footer.svelte';

</script>

<div class="relative flex flex-col max-w-[1400px] mx-auto w-full text-sm sm:text-base min-h-screen">
  <div class="">
    <button>
      <i class="fa-solid fa-arrow-up"></i>
    </button>
  </div>

  <Header />

  <slot />

  <Footer />
</div>
