<script>
	import { onMount } from 'svelte';
	
	let greeting = 'Hello, Coolify! This is an update! Using uuid. Deploy permissions. Restarted.';
	let isDeployed = false;
	
	onMount(() => {
	  // This will only run in the browser
	  isDeployed = window.location.hostname !== 'localhost';
	});
  </script>
  
  <main>
	<h1>{greeting}</h1>
	
	<div class="card">
	  <p>
		{#if isDeployed}
		  🚀 Successfully deployed with Coolify!
		{:else}
		  🔧 Running in development mode
		{/if}
	  </p>
	</div>
	
	<p class="info">
	  Edit <code>src/routes/+page.svelte</code> to test automatic deployments
	</p>
	<p>Source folder is /Documents/dev/Coolify-Testing-Deployment/svelte-coolify-demo</p>
	<p>Changed Github webhook</p>
  </main>
  
  <style>
	main {
	  display: flex;
	  flex-direction: column;
	  align-items: center;
	  justify-content: center;
	  min-height: 100vh;
	  text-align: center;
	  padding: 1rem;
	  max-width: 800px;
	  margin: 0 auto;
	}
	
	h1 {
	  color: #ff3e00;
	  font-size: 4rem;
	  margin-bottom: 0.5rem;
	}
	
	.card {
	  padding: 2rem;
	  border-radius: 8px;
	  background-color: #f9f9f9;
	  box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
	  margin: 2rem 0;
	  width: 100%;
	  max-width: 500px;
	}
	
	.info {
	  color: #888;
	}
	
	code {
	  background-color: #f1f1f1;
	  padding: 0.2em 0.4em;
	  border-radius: 3px;
	}
  </style>