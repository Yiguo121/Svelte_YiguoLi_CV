<!-- EducationBackground.svelte -->
<script>
    export let isDarkMode = false;
    let isOpen = false;
  
    function toggleAccordion() {
      isOpen = !isOpen;
    }
  
    function applyTheme() {
      if (isDarkMode) {
        return {
          backgroundColor: '#1a202c',
          color: '#fff'
        };
      } else {
        return {
          backgroundColor: '#fff',
          color: '#000'
        };
      }
    }
  </script>
  
  <div class="mb-6" style="background-color: {applyTheme().backgroundColor}; color: {applyTheme().color}">
      <div class="flex justify-between items-center cursor-pointer mb-2" on:click={toggleAccordion}>
          <h2 class="text-2xl font-bold text-blue-600 mb-2">Education Background</h2>
          <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path x-show={isOpen} stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 15l7-7 7 7"></path>
              <path x-show={!isOpen} stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
          </svg>
      </div>
      {#if isOpen}
          <div class="mb-4">
              <p class="font-bold">ESSEC Business School</p>
              <p>Program: Grande Ecole (Master in Management)</p>
              <p class="mb-2">08.2022-Present</p>
          </div>
          <div>
              <p class="font-bold">Northeast Forestry University (NEFU), « Project 211 », Harbin, China</p>
              <p>Degree: Bachelor of Engineering, Major: Wood Science and Engineering</p>
              <p>09.2015-07.2019</p>
          </div>
      {:else}
          <div class="ml-6 italic">Click to expand for more details...</div>
      {/if}
  </div>
  