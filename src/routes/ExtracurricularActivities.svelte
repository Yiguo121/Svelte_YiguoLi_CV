<!-- ExtracurricularActivities.svelte -->
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
          <h2 class="text-2xl font-bold text-blue-600 mb-2">Extracurricular Activities</h2>
          <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path x-show={isOpen} stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 15l7-7 7 7"></path>
              <path x-show={!isOpen} stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
          </svg>
      </div>
      {#if isOpen}
          <div class="mb-6 ml-6">
              <h3 class="font-bold">Leader, Guitar Club, NEFU</h3>
              <p>Managed all club activities, recruitment of over 200 members annually, classroom rental, daily training, arts performances (9 campus activities), publicity, and guitar procurement</p>
              <p>Organized online activities to record musical compositions and promoted the final work as an article on the campus platform, receiving recognition as one of the Top 10 WeChat Pictures and Articles of NEFU in 2018</p>
              <p>Created a guitar version of the school song, garnering over 10,000 video views on NEFU's official media platforms</p>
              
              <h3 class="font-bold">Student, UpChord Electronic Music and Pop Music Production Course</h3>
              <p>Beijing, China</p>
              <p>Registered as a NetEase Cloud Musician and published music works</p>
          </div>
      {:else}
          <div class="ml-6 italic">Click to expand for more details...</div>
      {/if}
  </div>
  
  