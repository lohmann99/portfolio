<script>
	import Screen from '$lib/Screen.svelte';

	let wordbuffer = [];
	let wordlist = ['this', 'some', 'word', 'are', 'this', 'words', 'vim'];

	let interval = setInterval(() => {
		let rnLeft = Math.floor(Math.random() * 100);
		let rnWord = wordlist[Math.floor(Math.random() * (wordlist.length - 1))];
		wordbuffer = [...wordbuffer, { word: rnWord, h: -10, left: rnLeft }];
		console.log(wordbuffer);
		if (wordbuffer.length >= 3) {
			clearInterval(interval);
		}
	}, 3000);
</script>

<Screen {wordbuffer} />
