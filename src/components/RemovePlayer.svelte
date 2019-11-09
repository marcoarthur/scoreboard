<script>
  import { createEventDispatcher } from 'svelte';

  const dispatch = createEventDispatcher();

  export let player; 

  const onClick = (e) => {
    e.preventDefault();
    dispatch("rmplayer", player );
    player = {
      name: "",
      points: 0
    };
  };
</script>

<button class="btn btn-info" on:click={onClick}>Remove</button>

