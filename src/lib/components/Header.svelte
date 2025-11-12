<script>
  import { Building2 } from 'lucide-svelte';
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

      <!-- Placeholder for navigation (coming in next feature) -->
      <div class="text-gray-600 text-sm">
        Navigation Coming Soon
      </div>
    </div>
  </div>
</header>