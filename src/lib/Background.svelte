<script lang="ts">
  import type { IColors, IRank } from '../interfaces';

  export let rank: IRank;
  export let colors: IColors = {
    boy: 'bg-blue-100',
    girl: 'bg-pink-100'
  };

</script>

<div class="relative min-h-screen min-w-full">
  <div class="min-h-screen min-w-full flex">
    <div class="boy min-h-full {colors.boy}" style="--boy-syze: {rank.boy}%" />
    <div class="girl min-h-full {colors.girl}" style="--girl-size: {rank.girl}%" />
  </div>
  <div class="absolute top-0 left-0 min-w-full min-h-screen bg-transparent">
    <slot />
  </div>
</div>

<style lang="scss">
  .boy {
    min-width: var(--boy-syze);
  }

  .girl {
    min-width: var(--girl-size);
  }
</style>
