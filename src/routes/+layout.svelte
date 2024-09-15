<link
	rel="stylesheet"
	href="https://nordcdn.net/ds/css/3.2.1/nord.min.css"
	integrity="sha384-x2XdCI8Yog7KGRmrrGLegjFrrIYXEhGNxql/xEXdMoW5NkpEhlAkUHdQJxkL1vPg"
	crossorigin="anonymous"
/>
<script lang="ts">
	import '../app.css';
	import { ModeWatcher } from "mode-watcher";
	import Sun from "lucide-svelte/icons/sun";
    import Moon from "lucide-svelte/icons/moon";
	import { toggleMode } from "mode-watcher";
	import { Button } from "$lib/components/ui/button/index.js";
	import * as Card from "$lib/components/ui/card/index.js";
</script>
<ModeWatcher />
<Card.Root>
	<Card.Header style="padding:0.5rem;justify-content: space-between;flex-direction: row;">
		<Card.Title tag="h1" style="font-size: x-large;font-weight: bold;padding-top: 10px;">Hack ' N ' Seek NCB NFT</Card.Title>
		<Button on:click={toggleMode} variant="outline" size="icon">
			<Sun
			  class="h-[1.2rem] w-[1.2rem] rotate-0 scale-100 transition-all dark:-rotate-90 dark:scale-0"
			/>
			<Moon
			  class="absolute h-[1.2rem] w-[1.2rem] rotate-90 scale-0 transition-all dark:rotate-0 dark:scale-100"
			/>
			<span class="sr-only">Toggle theme</span>
		  </Button>
	</Card.Header>
</Card.Root>
<slot></slot>

