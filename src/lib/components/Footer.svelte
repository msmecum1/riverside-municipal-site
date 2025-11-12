<script>
  import { Mail, Phone, MapPin } from 'lucide-svelte';
</script>

<footer class="bg-gray-800 text-white mt-auto">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-12">
    <div class="grid grid-cols-1 md:grid-cols-3 gap-8">
      <!-- Contact Info -->
      <div>
        <h3 class="font-semibold text-lg mb-4">City of Riverside</h3>
        <div class="space-y-3">
          <div class="flex items-start">
            <MapPin class="w-5 h-5 mr-3 mt-0.5 flex-shrink-0" />
            <div class="text-gray-300 text-sm">
              <p>123 Main Street</p>
              <p>Riverside, TX 78000</p>
            </div>
          </div>
          <div class="flex items-center">
            <Phone class="w-5 h-5 mr-3 flex-shrink-0" />
            <a href="tel:+15551234567" class="text-gray-300 hover:text-white text-sm">
              (555) 123-4567
            </a>
          </div>
          <div class="flex items-center">
            <Mail class="w-5 h-5 mr-3 flex-shrink-0" />
            <a href="mailto:info@riverside.gov" class="text-gray-300 hover:text-white text-sm">
              info@riverside.gov
            </a>
          </div>
        </div>
      </div>

      <!-- Quick Links -->
      <div>
        <h3 class="font-semibold text-lg mb-4">Quick Links</h3>
        <ul class="space-y-2 text-sm">
          <li><a href="/employment" class="text-gray-300 hover:text-white">Employment</a></li>
          <li><a href="/public-records" class="text-gray-300 hover:text-white">Public Records</a></li>
          <li><a href="/accessibility" class="text-gray-300 hover:text-white">Accessibility</a></li>
          <li><a href="/sitemap" class="text-gray-300 hover:text-white">Site Map</a></li>
        </ul>
      </div>

      <!-- Hours -->
      <div>
        <h3 class="font-semibold text-lg mb-4">Office Hours</h3>
        <div class="text-gray-300 text-sm space-y-2">
          <p class="font-medium">Monday - Friday</p>
          <p>8:00 AM - 5:00 PM</p>
          <p class="mt-4">Closed on City Holidays</p>
        </div>
      </div>
    </div>

    <!-- Copyright -->
    <div class="border-t border-gray-700 mt-8 pt-8 text-center">
      <p class="text-sm text-gray-400">
        © {new Date().getFullYear()} City of Riverside, Texas. All rights reserved.
      </p>
      <p class="text-xs text-gray-500 mt-2">
        Website by <a href="https://madmecs.org" class="hover:text-gray-300" target="_blank" rel="noopener">Mad Mecs Web Development</a>
      </p>
    </div>
  </div>
</footer>