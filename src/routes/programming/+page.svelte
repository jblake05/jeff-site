<script>
    export let data;
</script>

<h1>programming projects</h1>

<!-- Read data from page.server.js that creates a ul for each in a const data -->
<ul>
	{#each data.summaries as {slug, title, description, images}}
		<li><a href="/progamming/{slug}">{title}</a></li>
	{/each}
</ul>