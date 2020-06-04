<script>
  import { createEventDispatcher } from "svelte";

  export let buttons;

  const dispatch = createEventDispatcher();
</script>

<style>
  button {
    font-family: "Nunito", sans-serif;
    display: block;
    font-size: 1.2rem;
    margin: 10px;
    transition: 1s;
    padding: 0.7em 1em;
    cursor: pointer;
    border-radius: 50px;
    background-color: #40b3ff;
    color: white;
    box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1),
      0 2px 4px -1px rgba(0, 0, 0, 0.06);
  }
</style>

{#each buttons as { value, text }}
  <button on:click={() => dispatch('click', { value })}>{text}</button>
{/each}
