<script lang="ts">
  import Fa from 'svelte-fa/src/fa.svelte'
  import {faChild, faChildDress} from '@fortawesome/free-solid-svg-icons'
  
  export let metrica: number = 50;

  function handleClickBoy() {
    metrica += 1
  }

  function handleClickGirl() {
    metrica -= 1
  }

</script>

<div class="h-24 w-96 bg-slate-50 rounded-md flex flex-col justify-center">
  <input class="" type="range" min="0" max="100" bind:value={metrica} hidden/>
  <div class="flex justify-between gap-0 h-full items-center">
    <button class="flex flex-col items-center justify-center font-bold w-full h-full hover:bg-blue-50" on:click={() => handleClickBoy()}>
      <span>
        <Fa icon={faChild} class="text-blue-600 text-xl"/>
      </span>
      menino
    </button>
    <button class="flex flex-col items-center justify-center font-bold w-full h-full hover:bg-pink-50" on:click={() => handleClickGirl() }>
      <Fa icon={faChildDress} class="text-pink-600 text-xl" />
      menina
    </button>
  </div>
</div>
