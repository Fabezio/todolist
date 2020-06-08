<script>
  import Todo from './Todo.svelte'
  // const todolist = [
  //   'essayer',
  //   'd\'afficher',
  //   'plusieurs lignes'

  // ]
  let categories = [
    {id: 0, name: "TYPE"},
    {id: 1, name: "courses"},
    {id: 2, name: "tâches"},
    {id: 3, name: "missions"},
    {id: 4, name: "devoirs"},
  ]

  let selected
  let entry = ""
  let entries = []
  function addEntry() {
    // console.log
    // if (event.which !== 13) return
    entries = [...entries, entry]
    // entry = ""
  }
  function emptyList() {
    entries.length = 0
    entry = ''
    // category = categories.id[0]

  }
  
  

</script>

<!-- <div>Aujourd'hui on va s'exercer à faire des pitis trucs sympas</div> -->
<select value={selected} >
  {#each categories as cat}
    <option value={cat}>{cat.name}</option>
  {/each}
</select>
<input type="text" bind:value={entry}>
<button on:click|preventDefault={addEntry}>Valider</button>
<p>{entry}</p>

<!-- <Todo caption="D'abord ajouter bootstrap" />
<Todo caption="ensuite tester differents scripts" />
{#each todolist as todo}
<Todo caption={todo} />
{/each} -->
<section>
{#each entries as todo}
<Todo class="todo">{todo}</Todo>
{/each}
</section>
<footer>
<slot />
<button id="emptylist" on:click={emptyList}>effacer la liste</button>
</footer>

<style>
  button {
    text-transform: uppercase;
  }
  section {
    max-height: 50vh;
    overflow-y: scroll;
    /* width: 50%;
    min-width: 480px;
    max-width: 768px; */
    text-align: center;
    margin: auto;
    padding: auto;
  }
  footer {
    position: fixed;
    bottom: 25px;
    width: 100%;
  }

  .todo {
    margin: auto;
    text-align: center;
  }
</style>