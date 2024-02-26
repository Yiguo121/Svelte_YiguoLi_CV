<!-- WorkExperiences.svelte -->
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
          <h2 class="text-2xl font-bold text-blue-600 mb-2">Work Experiences</h2>
          <svg class="w-6 h-6" fill="none" viewBox="0 0 24 24" stroke="currentColor">
              <path x-show={isOpen} stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 15l7-7 7 7"></path>
              <path x-show={!isOpen} stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
          </svg>
      </div>
      {#if isOpen}
          <div class="mb-6 ml-6">
              <h3 class="font-bold">Investment Banking (Bond Sector) Intern</h3>
              <p class="italic">Tianfeng Securities Co., Ltd., Shanghai, China</p>
              <p class="mb-2">07.2023-09.2023</p>
              <ul class="list-disc ml-6 mb-4">
                  <li>Drafted a comprehensive bond underwriting prospectus for a target company's bond issuance and produced two corporate semi-annual reports offering in-depth analysis and insights into business operations, market position and trends, and financial performance</li>
                  <li>Utilized proficiently data analysis tools like Wind for data extraction and analysis, providing valuable project support. Gathered information from exchanges and government websites to validate the analysis</li>
                  <li>Analyzed corporate financial statements. Conducted in-depth data analysis to thoroughly understand the issuer's financial condition and enhance decision-making processes</li>
                  <li>Participated in the bidding process and prepared bidding documents that accurately reflected the company's performance and credit history, while providing relevant supporting documentation</li>
              </ul>
              <h3 class="font-bold">Representative of the China Office</h3>
              <p class="italic">FrenchTimber, Paris/Shanghai, France/China</p>
              <p class="mb-2">07.2019-07.2022</p>
              <ul class="list-disc ml-6 mb-4">
                  <li>Conducted market research and collected import/export data in China and the United States. Created quarterly analytical reports for French headquarters</li>
                  <li>Managed marketing and communication. Publishing 76 articles and attracting 700+ followers on WeChat and LinkedIn. Established an online request platform, receiving 20+ purchase requests during covid lockdown</li>
                  <li>Organized wood exhibitions 5 times per year. Handled booth construction, logistics, and transportation. Developed and maintained customer relationships while conducting local market research. Provided relevant analysis and reports</li>
                  <li>Maintained operations of China Office. Facilitated effective communication with timber companies, providing valuable market information through slide presentations by using Tableau for the French timber industry</li>
              </ul>
          </div>
      {:else}
          <div class="ml-6 italic">Click to expand for more details...</div>
      {/if}
  </div>
  