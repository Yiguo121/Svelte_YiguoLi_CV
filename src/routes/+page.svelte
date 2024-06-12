<script>
  import './tailwind.css';
  import { onMount } from 'svelte';
  import AOS from 'aos';
  import 'aos/dist/aos.css';

  import Education from './Education.svelte';
  import ProfessionalExperience from './ProfessionalExperience.svelte';
  import ExtracurricularActivities from './ExtracurricularActivities.svelte';
  import DarkModeToggle from './DarkModeToggle.svelte';
  import ContactForm from './ContactForm.svelte';

  let isDarkMode = false;

  onMount(() => {
    AOS.init({ duration: 1200 });
  });
</script>

<style>
  /* Add your custom styles here if needed */
</style>

<div class={`bg-gray-100 dark:bg-gray-900 flex justify-center items-center min-h-screen`}>
  <div class="bg-white dark:bg-gray-800 dark:text-gray-200 shadow-2xl rounded-lg w-11/12 max-w-6xl flex overflow-hidden my-10 relative">
    <!-- Decorative background circles -->
    <div class="absolute -top-10 -left-10 w-32 h-32 bg-blue-300 dark:bg-blue-600 rounded-full mix-blend-multiply filter blur-2xl opacity-50"></div>
    <div class="absolute -bottom-10 -right-10 w-32 h-32 bg-yellow-300 dark:bg-yellow-600 rounded-full mix-blend-multiply filter blur-2xl opacity-50"></div>

    <div class="bg-gradient-to-b from-blue-500 to-blue-700 p-8 w-1/3 text-white flex flex-col items-center">
      <div class="text-center mb-8">
        <div class="text-4xl font-bold mb-4 border-b-4 border-white inline-block">Yiguo Li</div>
        <div class="text-lg font-semibold mt-4">Contact Information</div>
        <p class="mt-2">Email: <a href="mailto:B00802621@essec.edu" class="underline">B00802621@essec.edu</a></p>
        <p class="mt-1">Phone: <a href="tel:+330757652807" class="underline">+33 07 57 65 28 07</a></p>
      </div>
      <div class="flex-grow">
        <h2 class="text-2xl font-semibold bg-gradient-to-r from-green-400 to-blue-500 text-transparent bg-clip-text pb-2 mb-4">Skills & Hobbies</h2>
        <ul class="list-disc pl-5 space-y-2">
          <li><strong>Languages:</strong> Chinese – Native, English – Fluent (IELTS 7.5; GMAT 720), French – Advanced</li>
          <li><strong>IT Skills:</strong> Proficient in Microsoft Office (Excel, PowerPoint, Word), Adobe (Premiere, Photoshop)</li>
          <li><strong>Hobbies:</strong> Keyboard for 10 years, Swimming for 15 years, Events & galas hosting (over 20 times)</li>
        </ul>
      </div>
    </div>
    <div class="p-8 w-2/3 text-gray-800 dark:text-gray-200">
      <div class="mb-8 flex justify-between items-center">
        <h2 class="text-3xl font-semibold bg-gradient-to-r from-purple-400 to-pink-500 text-transparent bg-clip-text pb-2 mb-4">Objective</h2>
        <DarkModeToggle {isDarkMode} />
      </div>
      <p class="text-lg leading-relaxed">Seeking a 6-month internship in marketing starting July 2023 with strong experience in data analysis and event holding.</p>
      <Education />
      <ProfessionalExperience />
      <ExtracurricularActivities />
      <ContactForm />
    </div>
  </div>
</div>