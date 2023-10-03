<script>
	export let wordbuffer;

	let drop = setInterval(() => {
		wordbuffer.forEach((item) => {
			item.h = item.h + 1;
		});
		wordbuffer = [...wordbuffer];
	}, 1000 / 30);
</script>

<div class="container">
	<div class="screen">
		{#each wordbuffer as word}
			<div style="top:{word.h}px; left:{word.left}%;" class="word">
				{#each word.word.split('') as letter}
					<div class="letter">{letter}</div>
				{/each}
			</div>
		{/each}
	</div>
</div>

<style>
	.container {
		position: relative;
		width: 60vw;
		height: 30vw;
		background: #222;
		margin: auto;
		overflow: hidden;
	}

	.word {
		position: absolute;
		display: flex;
	}

	.letter {
		width: 30px;
		height: 30px;
		display: flex;
		justify-content: center;
		align-items: center;
		border: 2px solid black;
		border-radius: 30%;
		background: #f1f1f1;
		margin-left: 1px;
	}
</style>
