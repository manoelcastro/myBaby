<script lang="ts">
  import type { IPerson } from '../interfaces';
  export let people: IPerson[];
</script>

<div class="flex justify-between gap-28 h-36">
  <div class="h-full w-96 p-2 bg-slate-50 text-blue-600 border-blue-400 rounded-lg border-8 overflow-y-scroll scrollbar-thin scrollbar-thumb-blue-100 scrollbar-thumb-rounded">
    {#each people as person}
      {#if person.vote === 'boy'}
        <li class="list-none">{person.name}</li>
      {/if}
    {/each}
  </div>
  <div class="h-full w-96 p-2 bg-slate-50 text-pink-600 border-pink-400 rounded-lg border-8 overflow-y-scroll scrollbar-thin scrollbar-thumb-rounded scrollbar-thumb-pink-100">
    {#each people as person}
      {#if person.vote === 'girl'}
        <li class="list-none">{person.name}</li>
      {/if}
    {/each}
  </div>
</div>
