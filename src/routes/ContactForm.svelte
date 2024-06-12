<script>
    import { writable } from 'svelte/store';
    import { onMount } from 'svelte';
    import AOS from 'aos';
    import 'aos/dist/aos.css';
  
    let name = '';
    let email = '';
    let message = '';
    let formValid = false;
  
    const nameValid = writable(true);
    const emailValid = writable(true);
    const messageValid = writable(true);
    let submitStatus = '';
  
    function validateName() {
      nameValid.set(name.trim().length >= 3);
    }
  
    function validateEmail() {
      const emailPattern = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
      emailValid.set(emailPattern.test(email));
    }
  
    function validateMessage() {
      messageValid.set(message.trim().length > 0);
    }
  
    function validateForm() {
      validateName();
      validateEmail();
      validateMessage();
      $: formValid = $nameValid && $emailValid && $messageValid;
    }
  
    function handleSubmit(event) {
      event.preventDefault();
      validateForm();
      if (formValid) {
        setTimeout(() => {
          submitStatus = 'success';
          name = '';
          email = '';
          message = '';
          validateForm();
        }, 1000);
      } else {
        submitStatus = 'error';
      }
    }
  
    onMount(() => {
      AOS.init();
    });
  </script>
  
  <style>
  </style>
  
  <form on:submit={handleSubmit} class="space-y-4 p-4 bg-white dark:bg-gray-800 shadow-md rounded" data-aos="fade-up">
    <div>
      <label for="name" class="block text-sm font-medium text-gray-700 dark:text-gray-300">Name</label>
      <input id="name" type="text" bind:value={name} on:input={validateName}
        class="mt-1 block w-full p-2 border rounded dark:bg-gray-700 dark:border-gray-600 dark:text-gray-200" required />
      {#if !$nameValid}
        <p class="text-red-600 text-sm">Name must be at least 3 characters long.</p>
      {/if}
    </div>
  
    <div>
      <label for="email" class="block text-sm font-medium text-gray-700 dark:text-gray-300">Email</label>
      <input id="email" type="email" bind:value={email} on:input={validateEmail}
        class="mt-1 block w-full p-2 border rounded dark:bg-gray-700 dark:border-gray-600 dark:text-gray-200" required />
      {#if !$emailValid}
        <p class="text-red-600 text-sm">Please enter a valid email address.</p>
      {/if}
    </div>
  
    <div>
      <label for="message" class="block text-sm font-medium text-gray-700 dark:text-gray-300">Message</label>
      <textarea id="message" bind:value={message} on:input={validateMessage}
        class="mt-1 block w-full p-2 border rounded dark:bg-gray-700 dark:border-gray-600 dark:text-gray-200" rows="4" required></textarea>
      {#if !$messageValid}
        <p class="text-red-600 text-sm">Message cannot be empty.</p>
      {/if}
    </div>
  
    <button type="submit" class="bg-blue-500 text-white p-2 rounded" disabled={!formValid}>Submit</button>
  
    {#if submitStatus === 'success'}
      <p class="text-green-600 text-sm">Form submitted successfully!</p>
    {/if}
    {#if submitStatus === 'error'}
      <p class="text-red-600 text-sm">Please fill out the form correctly before submitting.</p>
    {/if}
  </form>
  