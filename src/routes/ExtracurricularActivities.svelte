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
  <h2 class="text-3xl font-semibold bg-gradient-to-r from-indigo-400 to-purple-500 text-transparent bg-clip-text pb-2 mb-4 cursor-pointer" on:click={toggle}>
    Extracurricular Activities
    <span class="ml-2">{isOpen ? '▲' : '▼'}</span>
    <span class="text-sm ml-2">{isOpen ? 'Click to collapse' : 'Click to expand'}</span>
  </h2>
  {#if isOpen}
  <ul class="space-y-6">
    <li>
      <p class="text-lg font-semibold"><strong>2018.09-2020.07</strong> Vice Director of the Art & Entertainment Dept. | Student Union of the French Department, SISU</p>
      <ul class="list-disc pl-5 space-y-1 text-base">
        <li>Planned and held 4 evening parties with 200+ participants, taking charge of venue layout design, equipment maintenance, lighting control, etc.</li>
        <li>Delivered a publicity presentation to introduce the Department during the freshers’ week, which attracted 100+ applicants, conducted recruitment interviews and provided freshmen training.</li>
        <li>Participated in promotional copywriting for department activities, achieving a reading volume of 1000+</li>
        <li>Wrote scripts and created introduction videos for different activities.</li>
      </ul>
    </li>
  </ul>
  {/if}
</div>
