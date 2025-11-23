<script>
  import { ChevronRight } from 'lucide-svelte';
  
  export let title;
  export let date;
  export let excerpt;
  export let slug;
</script>

<div class="border-b border-gray-200 pb-4 last:border-0">
  <div class="flex justify-between items-start mb-2">
    <h3 class="font-semibold text-lg text-gray-900 flex-grow">{title}</h3>
    <span class="text-sm text-gray-500 flex-shrink-0 ml-4 whitespace-nowrap">{date}</span>
  </div>
  <p class="text-gray-600 mb-3 line-clamp-2">{excerpt}</p>
  <a 
    href="/news/{slug}" 
    class="text-blue-600 text-sm font-semibold inline-flex items-center hover:text-blue-700 transition-colors"
  >
    Read more
    <ChevronRight class="w-4 h-4 ml-1" />
  </a>
</div>