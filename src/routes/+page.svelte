<script lang="ts">
  import Background from "$lib/Background.svelte";
  import Vote from '$lib/Vote.svelte'
  import Teams from '$lib/Teams.svelte'

  let metrica: number;

  $: boy = metrica
  $: girl = 100 - metrica

</script>

<Background rank={{boy, girl}}>
  <div class="min-h-screen min-w-full flex justify-center items-center">
    <div class="flex flex-col justify-between items-center gap-8">
      <Vote bind:metrica />
      <Teams />
    </div>
  </div>
</Background>
