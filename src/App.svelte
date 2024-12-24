<script lang="ts">
  import svelteLogo from "./assets/svelte.svg";
  import viteLogo from "/vite.svg";
  import Counter from "./lib/Counter.svelte";
  import Todo from "./lib/Todo.svelte";
  import TodoList from "./lib/TodoList.svelte";

  const task = {
    task: "Buy a new car",
    completed: false,
  };

  let todos = [
    { task: "Mow lawn", completed: false },
    { task: "Walk dog", completed: false },
    { task: "Read newspaper", completed: false },
  ];
</script>

<main>
  <div>
    <a href="https://vite.dev" target="_blank" rel="noreferrer">
      <img src={viteLogo} class="logo" alt="Vite Logo" />
    </a>
    <a href="https://svelte.dev" target="_blank" rel="noreferrer">
      <img src={svelteLogo} class="logo svelte" alt="Svelte Logo" />
    </a>
  </div>
  <h1>Vite + Svelte</h1>

  <div class="card">
    <Counter />
  </div>

  <div class="card">
    <h2>Data</h2>
    <Todo task="Eat something" />
    <Todo task="Buy PlayStation5" completed={true} />
    <Todo {...task} />
  </div>

  <div class="card">
    <h2>Loops & Conditionals</h2>
    {#each todos as todo}
      <Todo {...todo} />
    {/each}
    {#if todos.length === 0}
      <p>All done!</p>
    {:else if todos.length === 1}
      <p>Almost there!</p>
    {:else}
      <p>Keep going!</p>
    {/if}
  </div>

  <div class="card">
    <h2>Events</h2>
    <TodoList />
  </div>

  <p>
    Check out <a
      href="https://github.com/sveltejs/kit#readme"
      target="_blank"
      rel="noreferrer">SvelteKit</a
    >, the official Svelte app framework powered by Vite!
  </p>

  <p class="read-the-docs">Click on the Vite and Svelte logos to learn more</p>
</main>

<style>
  .logo {
    height: 6em;
    padding: 1.5em;
    will-change: filter;
    transition: filter 300ms;
  }
  .logo:hover {
    filter: drop-shadow(0 0 2em #646cffaa);
  }
  .logo.svelte:hover {
    filter: drop-shadow(0 0 2em #ff3e00aa);
  }
  .read-the-docs {
    color: #888;
  }
</style>
