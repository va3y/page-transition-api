<script lang="ts">
	import Link from 'src/compoents/Link.svelte';
</script>

<main class="bg-purple-500">
	<h1>Page transitions api demo</h1>
	<p>This feature is still in development. Make sure to enable the flag Chrome settings!</p>
	<p>chrome://flags/#document-transition;</p>
	<Link href="/another-page">go to another page</Link>
</main>

<style global>
	@keyframes slide-to-left {
		to {
			transform: translateX(-100%);
		}
	}

	@keyframes slide-from-right {
		from {
			transform: translateX(100%);
		}
	}

	::page-transition-outgoing-image(root) {
		animation: 500ms ease-in-out both slide-to-left;
	}

	::page-transition-incoming-image(root) {
		animation: 500ms ease-in-out both slide-from-right;
	}
</style>
