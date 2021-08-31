<script>
  let tasks = [
    { done: false, text: 'Access Control' },
    { done: false, text: 'Fuel Site Controller' },
    { done: false, text: 'Domain Account' },
    { done: false, text: 'Yubikey Programmed' },
    { done: false, text: 'Office 365 Account' },
    { done: false, text: 'Phone extention in 3cx setup' },
    { done: false, text: 'Time Clock Plus Setup' },
    { done: false, text: 'Ensure registration for Security Awareness' },
  ];

  function add() {
    tasks = tasks.concat({ done: false, text: '' });
  }

  function clear() {
    tasks = tasks.filter(t => !t.done);
  }

  $: remaining = tasks.filter(t => !t.done).length;
</script>

{#each tasks as task}
  <div class:done={task.done}>
    <input
      type=checkbox
      bind:checked={task.done}
    >

    <input
      placeholder="What needs added to the list?"
      bind:value={task.text}
    >
  </div>

  {/each}

  <p>{remaining} remaining  </p>

  <button on:click={add}>Add to list</button>
  <button on:click={clear}>Clear Completed</button>
  <!-- TODO make this a reset back to starter list -->

  <style>
    .done{
      opacity: 0.4;
    }
  </style>

