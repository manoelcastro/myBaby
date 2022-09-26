<script lang="ts">
  import girl from '$lib/assets/girl.png'
  import boy from '$lib/assets/boy.png'
  

  export let metrica: number = 50;

  function handleClickBoy() {
    if (metrica < 100) metrica += 1;
  }

  function handleClickGirl() {
    if (metrica > 0) metrica -= 1;
  }
</script>

<div class="h-24 w-96 bg-slate-50 rounded-md flex flex-col justify-center overflow-hidden">
  <input class="" type="range" min="0" max="100" bind:value={metrica} hidden />
  <div class="flex justify-between gap-0 h-full items-center">
    <button
      class="flex flex-col items-center justify-center font-bold w-full h-full hover:bg-blue-50"
      on:click={() => handleClickBoy()}
    >
    <figure class="h-10">
      <img class="h-full w-full object-cover" src={boy} alt="girl" />
    </figure>
      menino
    </button>
    <button
      class="flex flex-col items-center justify-center font-bold w-full h-full hover:bg-pink-50"
      on:click={() => handleClickGirl()}
    >
      <figure class="h-10">
        <img class="h-full w-full object-cover" src={girl} alt="girl" />
      </figure>
      menina
    </button>
  </div>
</div>
