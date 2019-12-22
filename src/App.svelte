<script context="module">
  import Nav from "./components/Nav.svelte";
  import Card from "./components/Card.svelte";
  import Footer from "./components/Footer.svelte";
</script>

<svelte:head>
  <link
    href="https://unpkg.com/tailwindcss@^1.0/dist/tailwind.min.css"
    rel="stylesheet" />
  <script
    src="https://kit.fontawesome.com/3da10dcffb.js"
    crossorigin="anonymous">

  </script>
</svelte:head>

<div class="antialiased text-gray-900">
  <div class="bg-gray-200 min-h-screen">
    <Nav />
    <div class="flex flex-wrap justify-center">
      {#each Array(10) as _, i}
        <Card />
      {/each}
    </div>
    <Footer />
  </div>

</div>
