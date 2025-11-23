<script>
  import { Bell, Calendar, FileText, ChevronRight } from 'lucide-svelte';
  import NewsCard from '$lib/components/NewsCard.svelte';
  
  const quickLinks = [
    {
      icon: Bell,
      title: 'Public Notices',
      description: 'Stay informed about city announcements and public hearings',
      link: '/agendas'
    },
    {
      icon: Calendar,
      title: 'Events Calendar',
      description: 'Check out upcoming community events and meetings',
      link: '/news'
    },
    {
      icon: FileText,
      title: 'City Documents',
      description: 'Access permits, forms, and official documents',
      link: '/departments'
    }
  ];
  
  const newsItems = [
    {
      title: 'City Council Meeting - November 15, 2025',
      date: 'Nov 8, 2025',
      excerpt: 'Join us for the regular city council meeting to discuss upcoming projects and budget allocations. Public comment period will be held.',
      slug: 'city-council-meeting-nov-15'
    },
    {
      title: 'Winter Festival Registration Open',
      date: 'Nov 5, 2025',
      excerpt: 'Registration is now open for vendors and participants in our annual Winter Festival. Limited vendor spaces available.',
      slug: 'winter-festival-registration'
    },
    {
      title: 'Street Maintenance Schedule Released',
      date: 'Nov 1, 2025',
      excerpt: 'View the schedule for upcoming street maintenance and construction projects in your area. Traffic updates available.',
      slug: 'street-maintenance-schedule'
    }
  ];
</script>

<svelte:head>
  <title>City of Riverside, Texas - Official Website</title>
  <meta name="description" content="Welcome to the City of Riverside, Texas. Your source for local government information, services, and community events." />
</svelte:head>

<div class="bg-gray-50">
  <!-- Hero Section -->
  <div class="bg-gradient-to-r from-blue-600 to-blue-800 text-white">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-16 md:py-24">
      <div class="max-w-3xl">
        <h1 class="text-4xl md:text-5xl lg:text-6xl font-bold mb-4 leading-tight">
          Welcome to Riverside
        </h1>
        <p class="text-xl md:text-2xl text-blue-100 mb-8">
          A proud Texas community serving our residents with excellence, transparency, and innovation
        </p>
        <div class="flex flex-col sm:flex-row gap-4">
          <a 
            href="/government" 
            class="inline-flex items-center justify-center bg-white text-blue-600 px-6 py-3 rounded-lg font-semibold hover:bg-blue-50 transition-colors"
          >
            Learn About Our City
            <ChevronRight class="w-5 h-5 ml-2" />
          </a>
          <a 
            href="/contact" 
            class="inline-flex items-center justify-center bg-blue-500 text-white px-6 py-3 rounded-lg font-semibold hover:bg-blue-400 transition-colors border-2 border-blue-500"
          >
            Contact Us
          </a>
        </div>
      </div>
    </div>
  </div>

  <!-- Quick Links Section -->
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
      {#each quickLinks as link}
        <div class="bg-white rounded-lg shadow-md border border-gray-200 p-6 hover:shadow-lg transition-shadow">
          <div class="flex items-start mb-4">
            <div class="flex-shrink-0">
              <div class="flex items-center justify-center h-12 w-12 rounded-md bg-blue-500 text-white">
                <svelte:component this={link.icon} class="w-6 h-6" />
              </div>
            </div>
          </div>
          <h3 class="text-lg font-semibold text-gray-900 mb-2">{link.title}</h3>
          <p class="text-gray-600 mb-4">{link.description}</p>
          <a 
            href={link.link} 
            class="text-blue-600 font-semibold inline-flex items-center hover:text-blue-700 transition-colors"
          >
            Explore
            <ChevronRight class="w-4 h-4 ml-1" />
          </a>
        </div>
      {/each}
    </div>
  </div>

  <!-- News Section -->
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
    <div class="bg-white rounded-lg shadow-md border border-gray-200 p-6 md:p-8">
      <div class="flex justify-between items-center mb-8">
        <div>
          <h2 class="text-3xl font-bold text-gray-900">Latest News & Announcements</h2>
          <p class="text-gray-600 mt-2">Stay updated with important city information</p>
        </div>
        <a 
          href="/news" 
          class="hidden md:inline-flex text-blue-600 font-semibold hover:text-blue-700 transition-colors"
        >
          View All →
        </a>
      </div>
      
      <div class="space-y-6">
        {#each newsItems as news}
          <NewsCard {...news} />
        {/each}
      </div>

      <div class="mt-8 pt-8 border-t border-gray-200">
        <a 
          href="/news" 
          class="inline-flex items-center text-blue-600 font-semibold hover:text-blue-700 transition-colors"
        >
          View All News →
        </a>
      </div>
    </div>
  </div>

  <!-- CTA Section -->
  <div class="bg-blue-50 border-t border-gray-200">
    <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
      <div class="rounded-lg bg-white border-2 border-blue-200 p-8 md:p-12 text-center">
        <h2 class="text-2xl md:text-3xl font-bold text-gray-900 mb-4">
          Have Questions?
        </h2>
        <p class="text-gray-600 mb-6 max-w-2xl mx-auto">
          Our city government is here to serve you. Contact any of our departments or reach out to city hall directly.
        </p>
        <a 
          href="/contact" 
          class="inline-flex items-center bg-blue-600 text-white px-8 py-3 rounded-lg font-semibold hover:bg-blue-700 transition-colors"
        >
          Get in Touch
          <ChevronRight class="w-5 h-5 ml-2" />
        </a>
      </div>
    </div>
  </div>
</div>