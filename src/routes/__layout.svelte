<script>
	import '../app.css';
	import { Footer, Navbar, ToggleThemeButton } from '$lib';
</script>

<div class="flex flex-col h-screen">
	<Navbar appName="Nimbyte">
		<div slot="navbar-end">
			<ToggleThemeButton btnClass="text-3xl" />
		</div>
	</Navbar>
	<main class="container grow w-11/12 mx-auto my-4">
		<slot />
	</main>
	<Footer twitter="NimbyteBlog" />
</div>
