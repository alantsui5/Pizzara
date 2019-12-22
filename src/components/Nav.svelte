<script>
  import { fade, slide } from "svelte/transition";
  import Account from "./AccountsDropdown.svelte";
  let isOpen = false;
</script>

<style>
  a {
    color: black;
  }
  i {
    text-align: center;
    vertical-align: middle;
    position: relative;
  }
  .badge:after {
    content: attr(data-count);
    position: absolute;
    background: #f56565;
    height: 1rem;
    bottom: 0rem;
    right: 0rem;
    width: 1rem;
    text-align: center;
    font-size: 0.7rem;
    border-radius: 50%;
    color: white;
    border: none;
  }
</style>

<header
  class="bg-white sm:flex sm:justify-between sm:items-center sm:px-4 sm:py-3">
  <div class="flex item-center justify-between px-4 py-3 sm:p-0">
    <div>
      <i class="text-red-600 fas fa-pizza-slice fa-2x m-0 p-0" />
      <span class="font-bold text-3xl text-gray-800">
        Pizza
        <i class="text-red-500 font-bold text-3xl">ra</i>
      </span>

    </div>

    <div class="sm:hidden">
      <button
        class="block text-red-400 hover:text-red-500 focus:text-red-500
        outline-none mt-2"
        on:click={() => (isOpen = !isOpen)}>
        <svg class="h-6 w-6 fill-current" viewBox="0 0 24 24">
          {#if isOpen == false}
            <path
              transition:fade
              fill-rule="evenodd"
              d="M4 5h16a1 1 0 0 1 0 2H4a1 1 0 1 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1
              1 0 0 1 0-2zm0 6h16a1 1 0 0 1 0 2H4a1 1 0 0 1 0-2z" />
          {:else}
            <path
              transition:fade
              fill-rule="evenodd"
              d="M18.278 16.864a1 1 0 0 1-1.414 1.414l-4.829-4.828-4.828 4.828a1
              1 0 0 1-1.414-1.414l4.828-4.829-4.828-4.828a1 1 0 0 1
              1.414-1.414l4.829 4.828 4.828-4.828a1 1 0 1 1 1.414 1.414l-4.828
              4.829 4.828 4.828z" />
          {/if}
        </svg>
      </button>
    </div>
  </div>

  <nav transition:slide class="sm:block" class:hidden={isOpen === false}>
    <div class="px-2 pt-2 pb-4 sm:flex sm:p-0">
      <a
        href="/"
        class=" block px-2 py-1 sm:inline-block font-semibold rounded
        hover:bg-red-400 hover:text-white hover:no-underline sm:ml-2">
        All Pizzas
      </a>
      <a
        href="/"
        class="mt-1 block px-2 py-1 font-semibold rounded hover:bg-red-400
        hover:text-white hover:no-underline sm:mt-0 sm:ml-2">
        Trending
      </a>

      <a
        href="/"
        class="mt-1 block px-2 py-1 font-semibold rounded hover:bg-red-400
        hover:text-white hover:no-underline sm:mt-0 sm:ml-2 hidden sm:block">
        <i class="fas fa-shopping-cart" />

      </a>
      <Account />
    </div>
    <div class="px-4 py-5 border-t border-gray-100 sm:hidden">
      <div class="flex justify-between items-center">
        <div class="flex items-center">
          <img
            class="h-8 w-8 border-2 border-gray-600 rounded-full object-cover"
            src="https://images.unsplash.com/photo-1487412720507-e7ab37603c6f?ixlib=rb-1.2.1&ixid=eyJhcHBfaWQiOjEyMDd9&auto=format&fit=crop&w=256&q=80"
            alt="Your avatar" />
          <span class="ml-3 font-semibold">Jane Doe</span>
        </div>
        <i data-count="3" class="fas fa-shopping-cart fa-2x badge" />
      </div>

      <div class="mt-4">
        <a
          href="/"
          class="block text-gray-400 hover:text-white rounded hover:bg-red-400
          hover:no-underline">
          Account settings
        </a>
        <a
          href="/"
          class="mt-2 block text-gray-400 hover:text-white rounded
          hover:bg-red-400 hover:no-underline hidden sm:block">
          Shopping Cart
        </a>
        <a
          href="/"
          class="mt-2 block text-gray-400 hover:text-white rounded
          hover:bg-red-400 hover:no-underline">
          Sign out
        </a>
      </div>
    </div>
  </nav>

</header>
