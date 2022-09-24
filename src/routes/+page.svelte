<script lang="ts">
  import type { IPerson } from '../interfaces';
  import Background from '$lib/Background.svelte';
  import Vote from '$lib/Vote.svelte';
  import Teams from '$lib/Teams.svelte';
  import person1 from '$lib/assets/person1.jpeg';

  console.log(person1);
  const people: IPerson[] = [
    {
      name: 'Joaquim Pereira',
      avatar: person1,
      vote: 'boy',
      pix: false
    },
    {
      name: 'Manoel Castro',
      avatar: '/',
      vote: 'girl',
      pix: true
    },
    {
      name: 'Sara Castro',
      avatar: '/',
      vote: 'girl',
      pix: true
    },
    {
      name: 'Lucelia Castro',
      avatar: '/',
      vote: 'girl',
      pix: true
    },
    {
      name: 'Samir Souza',
      avatar: '/',
      vote: 'boy',
      pix: true
    },
    {
      name: 'Lucy Duarte',
      avatar: '/',
      vote: 'boy',
      pix: true
    },
    {
      name: 'Lucilly Duarte',
      avatar: '/',
      vote: 'girl',
      pix: true
    },
        {
      name: 'Joaquim Pereira',
      avatar: person1,
      vote: 'boy',
      pix: false
    },
    {
      name: 'Manoel Castro',
      avatar: '/',
      vote: 'girl',
      pix: true
    },
    {
      name: 'Sara Castro',
      avatar: '/',
      vote: 'girl',
      pix: true
    },
    {
      name: 'Lucelia Castro',
      avatar: '/',
      vote: 'girl',
      pix: true
    },
    {
      name: 'Samir Souza',
      avatar: '/',
      vote: 'boy',
      pix: true
    },
    {
      name: 'Lucy Duarte',
      avatar: '/',
      vote: 'boy',
      pix: true
    },
    {
      name: 'Lucilly Duarte',
      avatar: '/',
      vote: 'girl',
      pix: true
    }
  ];

  let metrica: number;

  $: boy = metrica;
  $: girl = 100 - metrica;
</script>

<Background rank={{ boy, girl }}>
  <div class="min-h-screen min-w-full flex justify-center items-center">
    <div class="flex flex-col justify-between items-center gap-8">
      <Vote bind:metrica />
      <Teams {people} />
    </div>
  </div>
</Background>
