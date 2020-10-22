<script>
	let blocks = [
		{
			name: "red",
			visibility: true,
		},
		{
			name: "blue",
			visibility: true,
		},
		{
			name: "green",
			visibility: true,
		},
	];

	function changeVisibility() {
		const { target } = event;
		blocks = blocks.map((block) => {
			return block.name === target.dataset.color
				? { ...block, visibility: false }
				: { ...block, visibility: true };
		});
	}
</script>

<style>
	.two {
		display: flex;
		justify-content: space-around;
		padding-top: 50px;
	}
	.block {
		width: 250px;
		height: 250px;
		display: none;
	}
	.red {
		background: red;
	}
	.blue {
		background: blue;
	}
	.green {
		background: green;
	}

	.visibility {
		display: block;
	}
</style>

<section class="two">
	{#each blocks as { name, visibility }}
		<div
			class="{visibility ? 'visibility' : ''} block {name}"
			on:click={changeVisibility}
			data-color={name} />
	{/each}
</section>
