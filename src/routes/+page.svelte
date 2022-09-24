<script lang="ts">
  import Background from "$lib/Background.svelte";
  import Vote from '$lib/Vote.svelte'
  import Teams from '$lib/Teams.svelte'

  interface IPerson {
      name: string;
      avatar: string;
      vote: string;
      pix: boolean;
  }

  const people: IPerson[] = [
    {
      name: 'Joaquim Pereira',
      avatar: '/',
      vote: 'boy',
      pix: false
    },
    {
      name: 'Manoel Castro',
      avatar: '/',
      vote: 'girl',
      pix: true
  }
]

  let metrica: number;

  $: boy = metrica
  $: girl = 100 - metrica

</script>

<Background rank={{boy, girl}}>
  <div class="min-h-screen min-w-full flex justify-center items-center">
    <div class="flex flex-col justify-between items-center gap-8">
      <Vote bind:metrica />
      <Teams {people} />
    </div>
  </div>
</Background>
