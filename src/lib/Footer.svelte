<script lang="ts">
	import Fa from 'svelte-fa';
	import { faTwitter } from '@fortawesome/free-brands-svg-icons';
	export let twitter = '';
	$: twitterURL = `https://twitter.com/${twitter}`;
</script>

<footer class="footer p-10 bg-base-200 text-base-content">
	<div>
		<span class="footer-title">Projects</span>
		<a class="link link-hover" href="https://blog.nimbyte.com">Blog</a>
		<a class="link link-hover" href="https://chat.nimbyte.com">Chat</a>
		<a class="link link-hover" href="https://tools.nimbyte.com">Tools</a>
	</div>
	<div>
		<span class="footer-title">Company</span>
		<a class="link link-hover" href="https://www.nimbyte.com/about-nimbyte">About Nimbyte</a>
		<a class="link link-hover" href="mailto:info@nimbyte.com">Contact</a>
	</div>
</footer>
<footer class="footer px-10 py-4 border-t bg-base-200 text-base-content border-base-300">
	<div class="items-center grid-flow-col">
		<p>© 2022 Nimbyte - All rights reserved</p>
	</div>
	{#if twitter}
		<div class="md:place-self-center md:justify-self-end">
			<div class="grid grid-flow-col gap-4 text-2xl">
				{#if twitter}
					<a href={twitterURL} target="_blank" class="hover:opacity-50">
						<Fa icon={faTwitter} fw />
					</a>
				{/if}
			</div>
		</div>
	{/if}
</footer>
