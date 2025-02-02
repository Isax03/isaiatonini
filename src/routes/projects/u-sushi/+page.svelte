<script lang="ts">
	import ProjectFeature from '$lib/components/projects/ProjectFeature.svelte';
    import Github from 'svelte-material-icons/Github.svelte';

	let loginDescr = "Login form for the three profiles (Admin, Kitchen and Customers).\nUsed custom auth system developed in Go with JWT tokens";
	let hosomakiDescr = "Menu page for the customers to order products. Divided in categories, products are displayed with their name, image and other details. They can be added to cart through the input field";
	let cartDescr = "Minimal cart page with summary of the order. The customer can send the order and the kitchen will receive it doing polling to the database.";
	let adminDesc = "Dashboard for the admin to manage the products, categories and other information. It also offers a password reset section for all the profiles.\n(The image shows the products management page)"
	let kitchenDesc = "Page that displays the orders received from the customers divided by table. For every dish, the kitchen can mark it as 'in progress', 'ready' or 'served'."
</script>

<div class="px-5 mt-12 mb-20 w-full items-center flex flex-col gap-12 text-primary-foreground">
	<div class="flex items-center gap-4">
		<p class="text-xl">Project for the Software Engineering course at University of Trento</p>
		<a href="https://github.com/USushi-G18" target="_blank" rel="noopener noreferrer" class="text-zinc-400 hover:text-secondary-foreground transition-colors">
			<Github size="1.5em"/>
		</a>
	</div>
	<div class="flex flex-col gap-10">
		<ProjectFeature title='Login' description={loginDescr} imageSrc="/projects/u-sushi/login.png" />
		<ProjectFeature title='Menu' description={hosomakiDescr} inverted imageSrc="/projects/u-sushi/hosomaki.png" />
		<ProjectFeature title='Cart' description={cartDescr} imageSrc="/projects/u-sushi/cart.png" />
		<ProjectFeature title='Admin Dashboard' description={adminDesc} inverted imageSrc="/projects/u-sushi/plates.png" />
		<ProjectFeature title='Kitchen' description={kitchenDesc} imageSrc="/projects/u-sushi/kitchen.png" />
		<p class="text-base text-center">Frontend in <a href="https://svelte.dev/" class="text-secondary-foreground">Svelte</a><br/>
			Backend in <a href="https://go.dev/" class="text-secondary-foreground">Go</a><br/>
			Database on <a href="https://www.postgresql.org/" class="text-secondary-foreground">PostgreSQL</a><br/>
		</p>
	</div>
</div>