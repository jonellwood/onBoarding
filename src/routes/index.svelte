<script>
  import FullTimePoliceFire from '../components/FullTimePoliceFire.svelte';
  import FullTimeAdmin from '../components/FullTimeAdmin.svelte';
  import Hidden from '../components/Hidden.svelte';
  import Footer from '../components/Footer.svelte';


  let types;
  let child;
  let parent;

  function handleSubmit() {
    alert('alert');
  }

</script>


<h1>Lets get onBoard!</h1>
<p>This is a dummy app and no one should ever use it ever</p>
<div class=wrapper>
  <button on:click={child.show}>Full Time Admin Employee</button>

  <Hidden bind:this={child} on:show={e => child.shown = e.detail}>
    <FullTimeAdmin />
  </Hidden>
  <hr/>
  <button on:click={parent.show}>Police or Fire Employee</button>

  <Hidden bind:this={parent} on:show={e => parent.shown = e.detail}>
    <FullTimePoliceFire />
  </Hidden>
</div>



<Footer />

 <style>
   body{
     font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
     padding: 0;
     margin: 0;
   }
   h1 {
     color: #ff3e00;
   }
   button{
    padding: 10px;
  }
  .wrapper{
    display: block;
  }

 </style>



