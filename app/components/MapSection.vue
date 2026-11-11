
<template>
  <section
    id="location"
    class="bg-[#303030] px-6 py-16 text-white"
  >
    <div class="max-w-4xl mx-auto">
      <h2 class="text-3xl font-bold text-[#ff3333] text-center mb-4">
        My Location
      </h2>

      <p class="text-gray-300 text-center mb-8">
        Explore my hometown, Cotabato City, Philippines.
      </p>

      <div
        ref="mapElement"
        class="w-full h-[400px] rounded-xl border-2 border-[#ff3333] shadow-lg overflow-hidden"
      ></div>

      <p class="text-center text-sm text-gray-400 mt-4">
        Satellite imagery provided by Esri.
      </p>
    </div>
  </section>
</template>

<script setup>
import { onMounted, onBeforeUnmount, ref } from 'vue'
import 'leaflet/dist/leaflet.css'

const mapElement = ref(null)
let map = null

onMounted(async () => {
  const L = await import('leaflet')

  // Initialize Map
  map = L.map(mapElement.value).setView(
    [7.2047, 124.2310],
    13
  )

  // Satellite Imagery Layer
  L.tileLayer(
    'https://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}',
    {
      attribution: 'Tiles &copy; Esri and its contributors',
      maxZoom: 19
    }
  ).addTo(map)

  // Location Marker
  L.marker([7.2047, 124.2310])
    .addTo(map)
    .bindPopup('Cotabato City, Philippines')
    .openPopup()
})

// Cleanup Map
onBeforeUnmount(() => {
  if (map) {
    map.remove()
    map = null
  }
})
</script>
