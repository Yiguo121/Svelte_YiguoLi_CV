<script>
  import { onMount } from 'svelte';
  import AOS from 'aos';
  import 'aos/dist/aos.css';

  let isOpen = false;

  function toggle() {
    isOpen = !isOpen;
  }

  onMount(() => {
    AOS.init();
  });
</script>

<div class="mb-8" data-aos="fade-up">
  <h2 class="text-3xl font-semibold bg-gradient-to-r from-yellow-400 to-red-500 text-transparent bg-clip-text pb-2 mb-4 cursor-pointer" on:click={toggle}>
    Education Background
    <span class="ml-2">{isOpen ? '▲' : '▼'}</span>
    <span class="text-sm ml-2">{isOpen ? 'Click to collapse' : 'Click to expand'}</span>
  </h2>
  {#if isOpen}
  <div>
    <p class="mb-4 text-lg"><strong>2022.09-Present</strong> Master in Management | Essec Business School - Program of Grand Ecole (GPA: 16.75/20)</p>
    <p class="text-lg"><strong>2018.09-2022.06</strong> Bachelor of Arts | Shanghai International Studies University (SISU) - Major in French (GPA: 3.44/4), Third Prize Merit Scholarship (Twice, 2020&2021)</p>
  </div>
  {/if}
</div>
