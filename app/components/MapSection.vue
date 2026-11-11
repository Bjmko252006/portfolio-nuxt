
<template>
  <section id="location" class="bg-[#303030] px-6 py-16 text-white">
    <div class="max-w-4xl mx-auto">

      <!-- Animated My Location Heading -->
      <h2
        class="location-font location-fire text-3xl font-bold text-center mb-4"
        data-text="My Location"
      >
        My Location
      </h2>

      <p class="location-font text-gray-300 text-center mb-8">
        Explore my hometown, Cotabato City, Philippines.
      </p>

      <div
        ref="mapElement"
        class="w-full h-[400px] rounded-xl border-2 border-[#ff3333] shadow-lg overflow-hidden"
      ></div>

      <p class="location-font text-center text-sm text-gray-400 mt-4">
        Satellite imagery by Esri. Place names and roads from OpenStreetMap.
      </p>
    </div>
  </section>
</template>

<script setup>
import { onMounted, onBeforeUnmount, ref } from 'vue'
import 'maplibre-gl/dist/maplibre-gl.css'
import workerUrl from 'maplibre-gl/dist/maplibre-gl-worker.mjs?worker&url'

const mapElement = ref(null)
let map = null

// Cotabato City coordinates [longitude, latitude]
const cotabatoCity = [124.2310, 7.2047]

onMounted(async () => {
  try {
    const maplibregl = await import('maplibre-gl')

    // Configure MapLibre worker for Nuxt and Vite
    maplibregl.setWorkerUrl(workerUrl)

    // Load OpenFreeMap vector style
    const response = await fetch(
      'https://tiles.openfreemap.org/styles/liberty'
    )

    if (!response.ok) {
      throw new Error('Unable to load OpenFreeMap style.')
    }

    const vectorStyle = await response.json()

    // Get label layers only
    const labelLayers = vectorStyle.layers.filter(
      layer => layer.type === 'symbol'
    )

    // Combine satellite imagery with map labels
    const satelliteStyle = {
      version: 8,
      name: 'Cotabato Satellite Map',
      glyphs: vectorStyle.glyphs,
      sprite: vectorStyle.sprite,

      sources: {
        ...vectorStyle.sources,

        satellite: {
          type: 'raster',
          tiles: [
            'https://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}'
          ],
          tileSize: 256,
          maxzoom: 19,
          attribution: 'Imagery © Esri and its contributors'
        }
      },

      layers: [
        {
          id: 'satellite-imagery',
          type: 'raster',
          source: 'satellite',
          minzoom: 0,
          maxzoom: 22
        },

        ...labelLayers
      ]
    }

    // Initialize map
    map = new maplibregl.Map({
      container: mapElement.value,
      style: satelliteStyle,
      center: cotabatoCity,
      zoom: 13,
      minZoom: 3,
      maxZoom: 19,
      attributionControl: true
    })

    // Zoom controls
    map.addControl(
      new maplibregl.NavigationControl(),
      'top-right'
    )

    // Add Cotabato City marker
    map.on('load', () => {
      new maplibregl.Marker({ color: '#ff3333' })
        .setLngLat(cotabatoCity)
        .setPopup(
          new maplibregl.Popup({ offset: 25 }).setHTML(
            '<strong>Cotabato City, Philippines</strong>'
          )
        )
        .addTo(map)
    })

    // Show map errors in browser console
    map.on('error', (event) => {
      console.error('Map loading error:', event.error)
    })

  } catch (error) {
    console.error('Unable to initialize satellite map:', error)
  }
})

onBeforeUnmount(() => {
  if (map) {
    map.remove()
    map = null
  }
})
</script>

<style scoped>
@import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800&display=swap');

/* LOCATION FONT */
.location-font {
  font-family: 'Orbitron', sans-serif;
  letter-spacing: 0.3px;
}

/* CENTERED VIOLET FLAME HEADING */
.location-fire {
  position: relative;
  display: table;
  width: fit-content;
  margin-left: auto;
  margin-right: auto;

  font-family: 'Orbitron', sans-serif;
  font-weight: 800;
  letter-spacing: 1px;
  line-height: 1.4;

  background: linear-gradient(
    180deg,
    #ffffff 0%,
    #faf5ff 35%,
    #e9d5ff 70%,
    #c084fc 100%
  );

  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;

  filter:
    drop-shadow(0 0 5px rgba(233, 213, 255, 0.9))
    drop-shadow(0 0 12px rgba(147, 51, 234, 0.6));

  animation: location-glow 2s ease-in-out infinite alternate;
}

/* VIOLET FLAME HIGHLIGHTS */
.location-fire::before {
  content: attr(data-text);
  position: absolute;
  inset: 0;

  background: linear-gradient(
    to top,
    transparent 10%,
    #a855f7 35%,
    #ffffff 55%,
    transparent 85%
  );

  background-clip: text;
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;

  filter: blur(5px);
  opacity: 0.65;
  pointer-events: none;

  animation: location-flame 1.5s ease-in-out infinite alternate;
}

/* GLOW ANIMATION */
@keyframes location-glow {
  from {
    filter:
      drop-shadow(0 0 4px rgba(233, 213, 255, 0.65))
      drop-shadow(0 0 9px rgba(147, 51, 234, 0.4));
  }

  to {
    filter:
      drop-shadow(0 0 8px rgba(255, 255, 255, 0.95))
      drop-shadow(0 0 18px rgba(147, 51, 234, 0.75));
  }
}

/* UPWARD FLAME MOVEMENT */
@keyframes location-flame {
  0% {
    transform: translateY(2px);
    opacity: 0.35;
    filter: blur(6px);
  }

  50% {
    transform: translateY(-2px);
    opacity: 0.8;
    filter: blur(4px);
  }

  100% {
    transform: translateY(-4px);
    opacity: 0.55;
    filter: blur(5px);
  }
}

/* ACCESSIBILITY */
@media (prefers-reduced-motion: reduce) {
  .location-fire,
  .location-fire::before {
    animation: none;
  }
}
</style>
