<script lang="ts">
  import type { IPerson } from '../interfaces';
  import Background from '$lib/Background.svelte';
  import Vote from '$lib/Vote.svelte';
  import Teams from '$lib/Teams.svelte';
  import person1 from '$lib/assets/person1.jpeg';
  import CallToAction from '$lib/CallToAction.svelte';
  import Rules from '$lib/Rules.svelte';

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

  let voted = false;

  let metrica: number
  
  $: boy = metrica;
  $: girl = 100 - metrica;
</script>

<Background rank={{ boy, girl }} >
  <div class="min-h-screen min-w-full flex justify-center items-center">
    <div class="min-w-full gap-28 flex flex-col items-center">
      {#if (!voted)}
      <Vote bind:metrica bind:voted />
      <h2 class="text-5xl text-pink-600 font-['Luckiest_Guy']">O que e, o que e?</h2>
      {:else}
      <Teams {people} />
      <p>Times feitos...</p>
      <p>Bora pro jogo!</p>
      {/if}
    </div>
  </div>
</Background>

<CallToAction />

<Rules />

