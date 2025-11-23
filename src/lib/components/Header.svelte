<script>
  import { Building2, Menu, X } from 'lucide-svelte';
  import Navigation from './Navigation.svelte';
  
  let mobileMenuOpen = false;
  
  function toggleMenu() {
    mobileMenuOpen = !mobileMenuOpen;
  }
  
  function closeMenu() {
    mobileMenuOpen = false;
  }
</script>

<header class="bg-white shadow-sm border-b border-gray-200 sticky top-0 z-50">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex justify-between items-center py-4">
      <!-- Logo and City Name -->
      <a href="/" class="flex items-center space-x-3 hover:opacity-80 transition">
        <div class="w-12 h-12 bg-blue-600 rounded-lg flex items-center justify-center">
          <Building2 class="w-7 h-7 text-white" />
        </div>
        <div>
          <h1 class="text-xl font-bold text-gray-900">City of Riverside</h1>
          <p class="text-sm text-gray-600">Texas</p>
        </div>
      </a>

      <!-- Desktop Navigation -->
      <div class="hidden md:block">
        <Navigation />
      </div>

      <!-- Mobile Menu Button -->
      <button 
        class="md:hidden p-2 rounded-lg hover:bg-gray-100 transition"
        on:click={toggleMenu}
        aria-label="Toggle menu"
        aria-expanded={mobileMenuOpen}
      >
        {#if mobileMenuOpen}
          <X class="w-6 h-6 text-gray-700" />
        {:else}
          <Menu class="w-6 h-6 text-gray-700" />
        {/if}
      </button>
    </div>
  </div>

  <!-- Mobile Navigation Menu -->
  {#if mobileMenuOpen}
    <div class="md:hidden border-t border-gray-200 bg-white pb-4">
      <div class="px-4 pt-2">
        <Navigation mobile={true} on:navigate={closeMenu} />
      </div>
    </div>
  {/if}
</header>