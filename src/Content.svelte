<script>
  import Todo from './Todo.svelte'
  const todolist = [
    'essayer',
    'd\'afficher',
    'plusieurs lignes'

  ]
  let entry = ""
  let entries = []
  function addEntry() {
    entries = [...entries, entry]
    entry = ""
  }
  

</script>

<!-- <div>Aujourd'hui on va s'exercer à faire des pitis trucs sympas</div> -->
<input type="text" bind:value={entry}>
<button on:click|preventDefault={addEntry}>Valider</button>
<p>{entry}</p>

<!-- <Todo caption="D'abord ajouter bootstrap" />
<Todo caption="ensuite tester differents scripts" />
{#each todolist as todo}
<Todo caption={todo} />
{/each} -->
{#each entries as todo}
<Todo caption={todo} />
{/each}
<footer>
<slot />
<button id="emptylist" on:click={() => entries.length=0}>effacer la liste</button>
</footer>

<style>
  button {
    text-transform: uppercase;
  }
  footer {
    position: fixed;
    bottom: 25px;
  }
</style>