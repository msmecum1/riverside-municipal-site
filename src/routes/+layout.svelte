<script>
  import '../app.css';
  import Header from '$lib/components/Header.svelte';
  import Footer from '$lib/components/Footer.svelte';
</script>

<svelte:head>
  <meta name="description" content="Official website of the City of Riverside, Texas" />
</svelte:head>

<div class="min-h-screen flex flex-col bg-gray-50">
  <Header />
  
  <main class="flex-grow">
    <slot />
  </main>
  
  <Footer />
</div>