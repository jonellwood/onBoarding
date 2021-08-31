<script>
  import FullTimePoliceFire from '../components/FullTimePoliceFire.svelte';
  import FullTimeAdmin from '../components/FullTimeAdmin.svelte';



  let types;


  function handleSubmit() {
    alert('alert');
  }

</script>


<h1>Lets get onBoard!</h1>
<p>This is a dummy app and no one should ever use it ever</p>

<label>
<input type=radio bind:group={types} value={1}>
Full Time Admin Employee
</label>

<label>
  <input type=radio bind:group={types} value={2}>
  Full Time Police or Fire
</label>
 {#if types}
 <FullTimeAdmin />
 <FullTimePoliceFire />
 {/if}




