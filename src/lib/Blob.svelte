<script>
	let blob;
</script>

<div
	on:pointermove={(event) => {
		const { clientX, clientY } = event;
		blob.animate(
			{
				left: `${clientX}px`,
				top: `${clientY}px`,
			},
			{ duration: 3000, fill: "forwards" }
		);
	}}
/>
<div id="blob" bind:this={blob} />


<style lang="postcss">
	div {
		position: fixed;
		z-index: 1;
		left: 0;
		top: 0;
		width: 100%;
		height: 100%;
		padding: 1rem;
		backdrop-filter: blur(100px);
	}

	#blob {
		width: 500px;
		height: 500px;
		z-index: -1;
		/* background: linear-gradient(to right, theme(colors.fuchsia.950), theme(colors.purple.500)); */
		background-image: linear-gradient(to right, #fa709a 0%, #fee140 100%);
		height: 250px;
		aspect-ratio: 1;
		position: absolute;
		left: 50%;
		right: 50%;
		translate: -50% -50%;
		border-radius: 50%;
		animation: rotate 10s infinite;
	}

	@keyframes rotate {
		from {
			rotate: 0deg;
		}
		50% {
			scale: 1 1.5;
		}
		to {
			rotate: 360deg;
		}
	}
</style>
