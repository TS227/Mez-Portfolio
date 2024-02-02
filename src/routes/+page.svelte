<script>
  import { slide, fade, fly } from 'svelte/transition';
  import mez1 from '../lib/images/mez1.webp';
    /**
     * @type {number}
     */

let y;
$: console.log(y);
</script>
<svelte:window bind:scrollY={y} />
<div class='w-4/5 mx-auto'>
  <div class="relative isolate px-6 pt-14 lg:px-8">
    <div class="mx-auto max-w-2xl py-40 sm:py-48 lg:py-56">
      <div class="mb-8 flex justify-center">
        <h3>Fashion & Interior Stylist</h3>
      </div>
      <div class="text-center">
        <h1 id='creating-the'class="text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">Creating The</h1>
        <h1 id='next-generation' class="text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">Next Generation</h1>
        <h1 id='of-fashion'class="text-4xl font-bold tracking-tight text-gray-900 sm:text-6xl">Of Fashion</h1>
      </div>
      <div class="mt-16 pb-48 md:pb-28 md:mb-16 flex justify-center">
        <a href="/about" class="text-lg font-semibold text-gray-900">Learn More</a>
      </div>
    </div>
  </div>
  {#if y >= 30}
    <h1 transition:slide={{ delay: 200, duration: 400 }} class="text-3xl font-bold underline">
      Hey! welcome to my portfolio :)
    </h1>
  {/if}
    {#if y >= 100}
      <div class='mt-3' transition:fade={{ delay: 600, duration: 700 }}>
        <p class='text-lg'>My name is mary-ann. i am currently a third year fashion communication & promotion student studying at nottingham trent university.
          I am a passionate creative wanting to express my thoughts and enthusiasm throughout my work, while also being detail-oriented and taking great pride in the work i produce.
        </p>
        {#if y >= 200}
          <div class="text-3xl mt-3 md:mt-8 font-bold underline" transition:fade={{delay: 300,duration: 900}}>
            <img src={mez1} alt="Mez" />
          </div>
        {/if}
      </div>
    {/if}
</div>

<style>
  @import url('https://fonts.googleapis.com/css2?family=Lobster&family=Mate+SC&family=Sansita+Swashed&display=swap');

  #creating-the {
    font-family: 'Sansita Swashed', cursive;
  }
  #next-generation {
    font-family: 'Lobster', cursive;
  }
  #of-fashion {
    font-family: 'Mate SC', serif;
  }
</style>
