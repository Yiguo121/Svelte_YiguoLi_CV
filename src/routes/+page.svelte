<script>
  import './tailwind.css';
  import Education from './Education.svelte';
  import WorkExperience from './WorkExperience.svelte';
  import ExtracurricularActivities from './ExtracurricularActivities.svelte';

  let isDarkMode = false;

  function toggleDarkMode() {
    isDarkMode = !isDarkMode;
    applyTheme();
  }

  function applyTheme() {
    if (isDarkMode) {
      document.body.style.backgroundColor = '#1a202c'; 
      document.body.style.color = '#fff'; 
    } else {
      document.body.style.backgroundColor = '#fff'; 
      document.body.style.color = '#000';
    }
  }

  function handleLinkedInSignIn() {
    window.location.href = 'https://www.linkedin.com/feed/?trk=guest_homepage-basic_nav-header-signin';
  }
</script>

<div class="container mx-auto my-10 p-6 bg-white shadow-lg rounded-lg">
  <button class="p-2 rounded-md bg-gray-200 hover:bg-gray-300" on:click={toggleDarkMode}>
    {isDarkMode ? "Switch to Light Mode" : "Switch to Dark Mode"}
  </button>

  <div class="flex flex-col lg:flex-row">
    <div class="lg:w-1/3 bg-blue-500 text-white p-4 space-y-4">
      <h1 class="text-3xl font-bold">Yuan GAO</h1>
      <p><i class="fas fa-phone mr-2"></i>+33-0757652830</p>
      <p><i class="fas fa-envelope mr-2"></i>yuan.gao@essec.edu</p>
      <p>LinkedIn: yuangao6688</p>
      <p>Looking for an internship starting in January 2024 (6 months)</p>
      <div class="mt-6">
        <h2 class="text-xl font-bold border-b-2 border-white pb-2">Additional Information</h2>
        <p>Language skills: Native in Chinese; fluent in English; intermediate in French (B2)</p>
        <p>Computer skills: MS Office, Tableau, Python, Adobe Photoshop, CAD, Ableton Live</p>
      </div>
    </div>
    <div class="lg:w-2/3 p-4 space-y-6">
      <Education {isDarkMode} {applyTheme} />
      <WorkExperience {isDarkMode} {applyTheme} />
      <ExtracurricularActivities {isDarkMode} {applyTheme} />
      <button class="fixed bottom-4 right-4 px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600" on:click={handleLinkedInSignIn}>
        Share
      </button>
    </div>
  </div>
</div>
