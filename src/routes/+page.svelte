<script>
    
    import NavBar from "$lib/components/navBar.svelte";
    import { onMount } from 'svelte';
    let map;
   
    import markerIcon2x from 'leaflet/dist/images/marker-icon-2x.png';
    import markerIcon from 'leaflet/dist/images/marker-icon.png';
    import markerShadow from 'leaflet/dist/images/marker-shadow.png';
    

    const portada = "/img/madrid450.png"
    const abono = "/servicios/abono.webp"
    const once = "/servicios/once.webp"
    const amazon = "/servicios/amazon.jpg"
    const nickel = "/servicios/nickel.jpg"
    const berger = "/servicios/berger.jpg"
    onMount(async () => {
    const L = await import('leaflet');

    map = L.map('map').setView([40.3865403, -3.7422629], 17);

    L.tileLayer('https://{s}.tile.openstreetmap.org/{z}/{x}/{y}.png', {
      attribution: '&copy; OpenStreetMap'
    }).addTo(map);

    L.marker([40.3865403, -3.7422629])
      .addTo(map)
      .bindPopup('Estanco 450');
  });

    
    
</script>
<main>
<NavBar />
<div class="flex flex-col gap-2 p-1">
    <div class="overflow-hidden w-full bg-amber-50 py-2">
        <p class="horario whitespace-nowrap text-center font-bold">
          Lunes - viernes : 8:30 - 20:30 · Sábados : 9:00 - 15:00 y 17:00 - 20:30 · Domingos y festivos: 10:00 - 14:00
        </p>
       
      </div>
       <p class="text-red-600 text-center text-[12px]">Prohibida la venta de productos del tabaco a menores de 18 años, conforme a la Ley 28/2005.</p>
      <div class="relative inline-block">
        <img src={portada} alt="portada" class="w-full rounded-xl brightness-75">
      
        <a
            href="/escaparate"
            class="absolute bottom-12 left-1/2 -translate-x-1/2
                p-3 bg-red-800 text-white font-bold
                rounded-xl shadow-lg
                hover:bg-red-700 transition">
            Escaparate
        </a>
      </div>
      <div class="max-w-5xl mx-auto px-4 py-8">
  <div class="grid grid-cols-2 sm:grid-cols-3 md:grid-cols-6 gap-6 text-center">

    <div class="flex flex-col items-center gap-2 p-4 border rounded-xl hover:bg-gray-100 transition">
      <span class="text-3xl">🥤</span>
      <p class="font-medium">Refrescos</p>
    </div>

    <div class="flex flex-col items-center gap-2 p-4 border rounded-xl hover:bg-gray-100 transition">
      <span class="text-3xl">🍬</span>
      <p class="font-medium">Caramelos</p>
    </div>

    <div class="flex flex-col items-center gap-2 p-4 border rounded-xl hover:bg-gray-100 transition">
      <span class="text-3xl">📱</span>
      <p class="font-medium">Recarga móvil</p>
    </div>

    <div class="flex flex-col items-center gap-2 p-4 border rounded-xl hover:bg-gray-100 transition">
      <span class="text-3xl">💳</span>
      <p class="font-medium">Recargas digitales</p>
    </div>

    <div class="flex flex-col items-center gap-2 p-4 border rounded-xl hover:bg-gray-100 transition">
      <span class="text-3xl">📡</span>
      <p class="font-medium">NFC</p>
    </div>

    <div class="flex flex-col items-center gap-2 p-4 border rounded-xl hover:bg-gray-100 transition">
      <span class="text-3xl">🐾</span>
      <p class="font-medium">Animal friendly</p>
    </div>

  </div>
</div>

      <div id="map" class="h-96 w-full rounded-xl"></div>
      <div class="grid grid-cols-2 gap-3 p-1">
        <img src={abono} alt="abono">
        <img src={once} alt="once">
        <img src={amazon} alt="amazon">
        <img src={berger} alt="berger">
        <img src={nickel} alt="nickel">
      </div>
      
</div>

</main>
<style>
    .horario {
  animation: scrollText 18s linear infinite;
}

@keyframes scrollText {
  0% {
    transform: translateX(100%);
  }
  100% {
    transform: translateX(-100%);
  }
}

</style>
