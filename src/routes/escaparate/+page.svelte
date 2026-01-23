<script>
    import NavBar from "$lib/components/navBar.svelte";
    import productosData from "$lib/assets/productos.json";
  
    const productos = productosData.productos;
  </script>
  
  <main>
    <NavBar />
  
    <div class="grid grid-cols-2 sm:grid-cols-2 md:grid-cols-3 gap-6 p-6">
      {#each productos as producto}
        <div class="border rounded-xl p-4 shadow hover:shadow-lg transition">
          <img
            src={producto.imagen}
            alt={producto.nombre}
            class="w-full h-48 object-cover rounded-lg mb-3"
          />
  
          <h2 class="font-bold text-lg">{producto.nombre}</h2>
  
          <p class="text-red-600 font-semibold">
            {producto.precio.toFixed(2).replace('.', ',')} €
          </p>
        </div>
      {/each}
    </div>
    <footer class="bg-red-700 text-white px-2 py-2">
      <div class="flex flex-col sm:flex-row items-center justify-between text-sm">
        <p>
          © {new Date().getFullYear()} · Todos los derechos reservados
        </p>
    
        <p class="opacity-80">
          Desarrollado por Madrid450
        </p>
      </div>
    </footer>
    
  </main>
  