<script lang="ts">
  import type { IPerson } from '../interfaces';
  export let people: IPerson[];
</script>

<div class="flex justify-between gap-28 h-60 text-sm font-['Cabin']">
  <div class="h-full w-96 p-2 bg-slate-50 text-blue-600 border-blue-400 rounded-lg border-8 overflow-y-scroll scrollbar-thin scrollbar-thumb-blue-100 scrollbar-thumb-rounded">
    {#each people as person}
      {#if person.vote === 'boy'}
        <li class="lista-boy list-none leading-9 font-light">{person.name}</li>
      {/if}
    {/each}
  </div>
  <div class="h-full w-96 p-2 bg-slate-50 text-pink-600 border-pink-400 rounded-lg border-8 overflow-y-scroll scrollbar-thin scrollbar-thumb-rounded scrollbar-thumb-pink-100">
    {#each people as person}
      {#if person.vote === 'girl'}
        <li class="lista-girl list-none leading-9 font-light">{person.name}</li>
      {/if}
    {/each}
  </div>
</div>
<style lang="scss">
  .lista-boy, .lista-girl {
    position: relative;
  }

  .lista-boy::after, .lista-girl::after {
    content: '';
    position: absolute;
    height: 0.1em;
    width: 5%;
    bottom: 0;
    left: 0;
    right: 0;
    margin: 0 auto;
  }

  .lista-girl::after {
    background-color: #fce7f3;
  }

  .lista-boy::after {
    background-color: #dbeafe;
  }
</style>
