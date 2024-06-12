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
  <h2 class="text-3xl font-semibold bg-gradient-to-r from-teal-400 to-blue-500 text-transparent bg-clip-text pb-2 mb-4 cursor-pointer" on:click={toggle}>
    Professional Experience
    <span class="ml-2">{isOpen ? '▲' : '▼'}</span>
    <span class="text-sm ml-2">{isOpen ? 'Click to collapse' : 'Click to expand'}</span>
  </h2>
  {#if isOpen}
  <ul class="space-y-6">
    <li>
      <p class="text-lg font-semibold"><strong>2021.12-2022.03</strong> Trade Marketing Intern | AB InBev</p>
      <ul class="list-disc pl-5 space-y-1 text-base">
        <li>Liaised with over 20 regional managers of 7 regions and 100+ channel merchants to provide materials for promotional activities and manage processes.</li>
        <li>Communicated with campaign suppliers to ensure the quality and quantity of promotional materials worth over 500k¥/70k€.</li>
        <li>Collaborated with the advertising agency on campaign planning; acted as a communication medium between the channel and the agency.</li>
      </ul>
    </li>
    <li>
      <p class="text-lg font-semibold"><strong>2021.07-2021.10</strong> Marketing CRM Dept. Intern | Christian Dior Couture</p>
      <ul class="list-disc pl-5 space-y-1 text-base">
        <li>Organized 3 online marketing events, communicating with a total of 10k+ guests.</li>
        <li>Participated in project management, communicated with Party B on proposals, and coordinated with internal departments (e.g., PR, legal) on project details.</li>
        <li>Produced weekly and monthly marketing data analysis reports to support strategy-making based on 30k+ data.</li>
        <li>Assisted with administrative work and file translation.</li>
      </ul>
    </li>
  </ul>
  {/if}
</div>
