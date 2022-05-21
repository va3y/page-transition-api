<script lang="ts">
	import { goto } from '$app/navigation';

	export let href: string;

	const onClick = async (e: MouseEvent) => {
		if (!('createDocumentTransition' in document)) {
			console.log('this feature is not supported');
			return;
		}

		e.preventDefault();

		const transition = (document as any).createDocumentTransition();
		await transition.start(async () => {
			await goto((e.target as HTMLAnchorElement).href);
		});
		console.log('Transition complete!');
	};
</script>

<a {href} on:click={onClick}><slot /></a>
