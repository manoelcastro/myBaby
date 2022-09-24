<script lang="ts">
  import Background from "$lib/Background.svelte";
  let metrica: number = 50;

  $: boy = metrica
  $: girl = 100 - metrica

  function handleClickBoy() {
    metrica += 1
  }

  function handleClickGirl() {
    metrica -= 1
  }

</script>

<Background rank={{boy, girl}}>
  <div class="min-h-screen min-w-full flex justify-center items-center">
    <div class="h-24 w-96 p-8 bg-slate-50 rounded-md flex flex-col justify-center">
      <input class="" type="range" min="0" max="100" bind:value={metrica} hidden/>
      <div class="flex justify-between">
        <button on:click={() => handleClickBoy()}>menino</button>
        <button on:click={() => handleClickGirl() }>menina</button>
      </div>
    </div>
  </div>
</Background>
