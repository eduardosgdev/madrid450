<script>
    import "../../app.css"
    import { goto } from "$app/navigation";
    let isOpen = false;
  
    function toggleMenu() {
      isOpen = !isOpen;
    }
  </script>
  <main class=" text-white px-2 py-2 bg-red-700 ">
    <!-- Contenedor principal de la navbar -->
    <nav class="flex items-center justify-between">
      <!-- Menú hamburguesa -->
        <button class="p-1 text-white hover:bg-gray-800 rounded" on:click={toggleMenu}>
          <!-- Ícono de menú (hamburguesa) -->
          <svg xmlns="http://www.w3.org/2000/svg" class="h-6 w-6 text-white" fill="none" viewBox="0 0 24 24" stroke="currentColor">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M4 6h16M4 12h16M4 18h16" />
          </svg>
        </button>
        <h2 class="font-bold">Madrid 450</h2>
        <button class="mr-4" on:click={() => goto('/cart')}>
          <svg class="w-8 h-8 text-white dark:text-white" aria-hidden="true" xmlns="http://www.w3.org/2000/svg" width="24" height="24" fill="none" viewBox="0 0 24 24">
            <path stroke="currentColor" stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 4h1.5L9 16m0 0h8m-8 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4Zm8 0a2 2 0 1 0 0 4 2 2 0 0 0 0-4Zm-8.5-3h9.25L19 7H7.312"/>
          </svg>
          
        </button>
      
    </nav>
  
    <!-- Menú desplegable en dispositivos móviles -->
    <div class={`lg:hidden ${isOpen ? 'block' : 'hidden'}  text-white  ml-2 text-[16px] font-semibold`}>
      <a href="/bares" class="block py-2 hover:bg-gray-800">Inicio</a>
      <a href="/escaparate" class="block py-2 hover:bg-gray-800">Escaparate</a>
      <a href="/aboutus" class="block py-2 hover:bg-gray-800">Nosotros</a>
      <a href="/contacto" class="block py-2 hover:bg-gray-800">Información </a>
  
    </div>
    
  </main>
  
  
  

  