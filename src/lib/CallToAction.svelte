<script lang="ts">
  import { onDestroy } from "svelte";
  import { fade, fly } from "svelte/transition";

  let visible = false;
  const interval = setInterval(() => visible = !visible, 1000)

  onDestroy(() => clearInterval(interval))
</script>

<div class="snap-start flex min-h-screen bg-slate-50 min-w-full">
  <div class="flex flex-col flex-1 pt-14 px-14">
    <h1 class="text-8xl font-bold text-slate-800 font-['Barlow']">Se liga na missao!</h1>
    <h2 class="text-2xl mt-8 font-bold text-fuchsia-700 font-['Barlow']">Nosso bebe esta chegando e a gente precisa de ajuda pra colocar as coisas no lugar antes del(e a) chegar...</h2>
    <p class="text-xl mt-6 font-normal text-slate-700 font-['Cabin']">Preparamos uma brincadeira e esperamos que voce se divirta enquanto nos ajuda nesse desafio.</p>
    <button class="self-center mt-28">
      {#if (visible)}
      <figure in:fade out:fly={{y: 100, duration: 2000}} class="h-12 w-20">
        <img src="/src/lib/assets/down-arrow.png" alt="">
      </figure>
      {/if}
    </button>
  </div>
  <div class="flex-1 max-h-screen overflow-hidden">
    <div style="width:100%;height:0;padding-bottom:178%;position:relative;">
      <iframe src="https://giphy.com/embed/VwX40PORzf3GMoFL6V" width="100%" height="100%" style="position:absolute;" frameBorder="0" class="giphy-embed" allowFullScreen>
      </iframe>
    </div>
  </div>
  
</div>
