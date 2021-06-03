<script>
  import { createEventDispatcher } from "svelte";

  const dispatch = createEventDispatcher();

  let player = {
    name: "",
    points: 0,
    type: "",
  };

  const onSubmit = (e) => {
    e.preventDefault();
    dispatch("addplayer", player);
    player = {
      name: "",
      points: 0,
      type: "",
    };
  };
</script>

<form on:submit={onSubmit} class="grid-3">
  <input type="text" placeholder="Player Name" bind:value={player.name} />
  <input type="number" placeholder="Player Points" bind:value={player.points} />
  <input type="text" placeholder="Machine Type" bind:value={player.type} />
  <input type="submit" class="btn btn-primary" value="Add Player" />
</form>
