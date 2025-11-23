<script>
  import { page } from '$app/stores';
  import { Home, Building2, Users, Newspaper, FileText, Phone } from 'lucide-svelte';
  import { createEventDispatcher } from 'svelte';
  
  export let mobile = false;
  
  const dispatch = createEventDispatcher();
  
  const navItems = [
    { href: '/', label: 'Home', icon: Home },
    { href: '/government', label: 'Government', icon: Building2 },
    { href: '/departments', label: 'Departments', icon: Users },
    { href: '/news', label: 'News', icon: Newspaper },
    { href: '/agendas', label: 'Agendas', icon: FileText },
    { href: '/contact', label: 'Contact', icon: Phone }
  ];
  
  $: currentPath = $page.url.pathname;
  
  function isActive(href) {
    if (href === '/') {
      return currentPath === '/';
    }
    return currentPath.startsWith(href);
  }
  
  function handleClick() {
    dispatch('navigate');
  }
</script>

{#if mobile}
  <!-- Mobile Navigation -->
  <nav class="flex flex-col space-y-1">
    {#each navItems as item}
      <a
        href={item.href}
        on:click={handleClick}
        class="flex items-center space-x-3 px-4 py-3 rounded-lg transition-colors {isActive(item.href)
          ? 'bg-blue-600 text-white font-semibold'
          : 'text-gray-700 hover:bg-gray-100'}"
      >
        <svelte:component this={item.icon} class="w-5 h-5" />
        <span>{item.label}</span>
      </a>
    {/each}
  </nav>
{:else}
  <!-- Desktop Navigation -->
  <nav class="flex space-x-1">
    {#each navItems as item}
      <a
        href={item.href}
        class="flex items-center space-x-2 px-4 py-2 rounded-lg transition-colors {isActive(item.href)
          ? 'bg-blue-600 text-white font-semibold'
          : 'text-gray-700 hover:bg-gray-100'}"
      >
        <svelte:component this={item.icon} class="w-4 h-4" />
        <span class="text-sm">{item.label}</span>
      </a>
    {/each}
  </nav>
{/if}