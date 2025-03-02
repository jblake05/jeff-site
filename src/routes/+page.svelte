<script>
	import { goto } from '$app/navigation';

	$: outerWidth = 0;
	$: innerWidth = 0;
	$: outerHeight = 0;
	$: innerHeight = 0;

	$: musicPoints = `0,0 0,${innerHeight} ${innerWidth / 2},${innerHeight}`;
	$: musicStyle = 'fill:#f76f81;';
	const musicRoute = () => {
		goto('/music');
	};

	$: progPoints = `0,0 ${innerWidth / 2},${innerHeight} ${innerWidth},0`;
	$: progStyle = 'fill:#fc92f7;';
	const progRoute = () => {
		goto('/programming');
	};

	$: aboutPoints = `${innerWidth},0 ${innerWidth},${innerHeight} ${innerWidth / 2},${innerHeight}`;
	$: aboutStyle = 'fill:#fcba8a;';
	const aboutRoute = () => {
		goto('/about');
	};
</script>

<svelte:window bind:innerWidth bind:outerWidth bind:innerHeight bind:outerHeight />

<!-- svelte-ignore a11y-click-events-have-key-events -->
<!-- svelte-ignore a11y-no-static-element-interactions -->
<svg width={innerWidth} height={innerHeight}>
	<!-- MUSIC -->
	<polygon
		points={musicPoints}
		on:click={musicRoute}
		on:mouseenter={() => {
			// musicStyle = "fill:#9d08d3;"
			musicStyle = 'fill:#ac90f9;';
		}}
		on:mouseleave={() => {
			musicStyle = 'fill:#f76f81;';
		}}
		style={musicStyle}
	/>

	<a
		href="/music"
		on:mouseenter={() => {
			musicStyle = 'fill:#ac90f9;';
		}}
	>
		<text x="12.5%" y="50%" dominant-baseline="middle" text-anchor="middle" fill="black">
			music
		</text>
	</a>

	<!-- PROGRAMMING -->
	<polygon
		points={progPoints}
		on:click={progRoute}
		on:mouseenter={() => {
			progStyle = 'fill:#92fcb7;';
		}}
		on:mouseleave={() => {
			progStyle = 'fill:#fc92f7;';
		}}
		style={progStyle}
	/>

	<a
		href="/programming"
		on:mouseenter={() => {
			progStyle = 'fill:#92fcb7;';
		}}
	>
		<text x="50%" y="50%" dominant-baseline="middle" text-anchor="middle" fill="black">
			programming
		</text>
	</a>

	<!-- ABOUT -->
	<polygon
		points={aboutPoints}
		on:click={aboutRoute}
		on:mouseenter={() => {
			aboutStyle = 'fill:#fcf392;';
		}}
		on:mouseleave={() => {
			aboutStyle = 'fill:#fcba8a;';
		}}
		style={aboutStyle}
	/>

	<a
		href="/about"
		on:mouseenter={() => {
			aboutStyle = 'fill:#fcf392;';
		}}
	>
		<text x="87.5%" y="50%" dominant-baseline="middle" text-anchor="middle" fill="black">
			about
		</text>
	</a>

	<!-- <polyline points={progPoints}></polyline> -->
</svg>

<!-- <style src="../styles/home.css"></style> -->
<style>
	polygon {
		stroke: black;
		stroke-width: 10px;
		stroke-opacity: 20%;
	}

	text {
		/* font-family: 'Courier New', Courier, monospace; */
		font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
		font-weight: 350;
		font-size: 25px;
	}
</style>
