<script>
  import Player from '../components/Player.svelte';
  import RemovePlayer from '../components/RemovePlayer.svelte';

  export let players;

  // remove player from players array
  const removePlayer = (e) => {
    const player = e.detail;
    var idx = players.indexOf(player);
    players.splice(idx,1);
    players = players; // this is need in order to re-render
  };
</script>

<div class="container">
  {#if players.length === 0}
    <p> No Players </p>
  {:else}
    {#each players as player}
      <Player name="{player.name}" points="{player.points}" />
      <RemovePlayer on:rmplayer={removePlayer} player={player}/>
    {/each}
  {/if}
</div>
