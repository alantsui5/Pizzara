<script>
  import { slide, fade } from "svelte/transition";
  let isOpen = false;
  const handleEscape = event => {
    if (event.key === "Esc" || event.key === "Escape") isOpen = false;
  };
</script>

<svelte:window on:keydown={handleEscape} />
<div class="relative hidden sm:block ml-6">
  <!-- remove edge outside block-->
  <button
    on:click={() => (isOpen = !isOpen)}
    class="block h-8 w-8 rounded-full overflow-hidden border-2 border-gray-600
    focus:outline-none focus:border-red-300">
    <img src="https://picsum.photos/35/35" alt="" />
  </button>
  {#if isOpen == true}
    <!--Button of focus & fade-->
    <span
      transition:fade
      on:click={() => (isOpen = false)}
      class="fixed top-0 right-0 h-full w-full bg-black opacity-50
      focus:bg-black focus:opacity-50" />
    <div
      transition:slide
      class="absolute right-0 w-48 bg-white rounded-lg py-2 shadow-md">
      <a
        href="/"
        class="block px-4 py-2 hover:bg-gray-600 hover:text-white
        hover:no-underline">
        Account Settings
      </a>
      <a
        href="/"
        class="block px-4 py-2 hover:bg-gray-600 hover:text-white
        hover:no-underline">
        Shopping Cart
      </a>
      <a
        href="/"
        class="block px-4 py-2 hover:bg-gray-600 hover:text-white
        hover:no-underline">
        Sign out
      </a>
    </div>
  {/if}
</div>
