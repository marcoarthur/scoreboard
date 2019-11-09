<script>
  import Navbar from './components/Navbar.svelte';
  import AddPlayer from './components/AddPlayer.svelte';
  import ListPlayer from './components/ListPlayer.svelte';

  let players = [
    {
      name: "Marco Silva",
      points: 100
    },
    {
      name: "Greice Montes",
      points: 200
    },
    {
      name: "Fulano Silva",
      points: 10
    }
  ];

  // add new player to players array
  const addPlayer = (e) => {
    const newPlayer = e.detail;
    players = [...players, newPlayer];
  };


</script>

<style>
  h1 {
    color: #204f6e;
  }
</style>

<Navbar />
<div class="container">
  <AddPlayer  on:addplayer={addPlayer}/>
  <ListPlayer bind:players />
</div>
