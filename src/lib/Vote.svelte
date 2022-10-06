<script lang="ts">
  import {fade} from 'svelte/transition'
  import girl from '$lib/assets/girl.png'
  import boy from '$lib/assets/boy.png'
  

  export let metrica: number = 50;
  export let voted = false;

  function handleClickBoy() {
    voted = true
    if (metrica < 100) metrica += 1;
  }

  function handleClickGirl() {
    voted = true
    if (metrica > 0) metrica -= 1;
  }
</script>

<div transition:fade class="h-48 w-3/4 bg-slate-50 rounded-md flex flex-col justify-center overflow-hidden">
  <input class="" type="range" min="0" max="100" bind:value={metrica} hidden />
  <div class="flex justify-between gap-0 h-full items-center text-2xl font-bold font-['Cabin'] text-slate-800">
    <button
      class="flex flex-col gap-3 items-center justify-center w-full h-full hover:bg-green-50"
      on:click={() => handleClickBoy()}
    >
    <figure class="h-10">
      <img class="h-full w-full object-cover" src={boy} alt="girl" />
    </figure>
      menino
    </button>
    <button
      class="flex flex-col gap-3 items-center justify-center w-full h-full hover:bg-fuchsia-50"
      on:click={() => handleClickGirl()}
    >
      <figure class="h-10">
        <img class="h-full w-full object-cover" src={girl} alt="girl" />
      </figure>
      menina
    </button>
  </div>
</div>
