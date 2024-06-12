<script>
  export let isDarkMode = false;

  function toggleDarkMode() {
    isDarkMode = !isDarkMode;
    document.documentElement.classList.toggle('dark', isDarkMode);
  }
</script>

<button class="p-2 bg-gray-200 dark:bg-gray-800 text-gray-800 dark:text-gray-200 rounded" on:click={toggleDarkMode}>
  {isDarkMode ? 'Light Mode' : 'Dark Mode'}
</button>
