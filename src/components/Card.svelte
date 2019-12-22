<script>
  import { pizza } from "../data/pizza.js";
</script>

<div
  class="bg-white rounded-lg overflow-hidden border m-6 shadow-xl w-4/5 md:w-2/5
  lg:w-64">
  <figure>
    <img src={pizza[0].imageUrl} alt={pizza[0].imageAlt} />
    <figcaption class="hidden">pizzfirea[0].imageAlt</figcaption>
  </figure>

  <div class="p-6">
    <div class="flex items-center">
      <span
        class="inline-block bg-red-200 text-red-700 text-xs uppercase
        font-semibold rounded-full px-2 py-1 tracking-wide">
        top 5
      </span>
      <div
        class="ml-2 text-gray-500 text-xs tracking-wide uppercase font-semibold
        tracking-wide">
        trending &bull trending
      </div>
    </div>
    <h4 class="mt-1 font-semibold text-lg leading-tight truncate">
      {pizza[0].title}
    </h4>
    <div>
      {pizza[0].formatedPrice}
      <span class="text-gray-600 text-sm">/price</span>
    </div>
    <div class="mt-2 flex items-center">
      {#each Array(5) as _, i}
        <i class="fas fa-star h-4 w-4" class:text-red-500={i < 3} />
      {/each}
      <span class="ml-4 text-gray-600 text-sm">
        {pizza[0].reviewCount}
        {pizza[0].reviewCount <= 1 ? 'review' : 'reviews'}
      </span>
    </div>
  </div>

</div>
