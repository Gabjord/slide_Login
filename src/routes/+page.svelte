<script>
	import { cubicIn, cubicOut, elasticIn, linear } from 'svelte/easing';

	import { fade, fly, slide } from 'svelte/transition';

	let signIn = true;

	let toggle = () => {
		signIn = !signIn;
	};
</script>

<!-- html -->
<main
	class=" flex h-screen w-screen flex-col items-center justify-center gap-y-3 overflow-hidden bg-[#f6f5f7]"
>
	<h1
		class="text-semibold w-fit rounded bg-orange-500 p-2 font-[1.1rem] text-white text-shadow-2xs text-shadow-black"
	>
		Coding Challenge
	</h1>
	<!-- sign in section -->
	{#if signIn}
		<section
			transition:fly={{ duration: 600, x: -300, easing: linear }}
			class="grid h-110 w-[52%] grid-cols-4 overflow-hidden rounded shadow-2xl shadow-black"
		>
			<!-- left -->
			<div
				class=" col-span-2 flex flex-col items-center justify-start gap-4 overflow-hidden rounded-lg rounded-r-none border border-transparent bg-white pt-15"
			>
				<h1 class="block font-sans text-[2rem] font-bold">Sign in</h1>
				<!-- icons -->
				<div class=" flex gap-3">
					<span class="size-8 rounded-full border border-[#DDDDDD] p-4"></span>
					<span class="size-8 rounded-full border border-[#DDDDDD] p-4"></span>
					<span class="size-8 rounded-full border border-[#DDDDDD] p-4"></span>
				</div>
				<p class="text-sm">or use your account</p>

				<form action="#" class="space-y-3">
					<input
						type="email"
						placeholder="Email"
						class="bg-[#eee] px-5 py-2 text-sm placeholder-[#333]"
					/><br />
					<input
						type="password"
						placeholder="Password"
						class="bg-[#eee] px-5 py-2 text-sm placeholder-[#333]"
					/>
				</form>
				<!-- forgotten link -->
				<a href="c" class="text-sm"> Forgot your password ?</a>

				<!-- sign In -->
				<button class="rounded-full bg-orange-500 px-10 py-2 text-sm font-semibold text-white"
					>Sign up</button
				>
			</div>
			<!-- right -->
			<div
				class="col-span-2 flex flex-col justify-center overflow-hidden rounded-lg rounded-l-none rounded-br-lg border-transparent bg-orange-500 text-center text-white shadow-2xl"
			>
				<h1 class="text-[2em] font-semibold">Hello, Friend!</h1>
				<p class="p-8 text-sm font-medium">Enter your personal details and start journey with us</p>
				<button
					on:click={toggle()}
					class="mx-auto w-fit rounded-full bg-white px-8 py-2 text-sm font-semibold text-orange-400"
					>SIGN UP
				</button>
			</div>
		</section>
	{/if}

	<!-- sign up -->
	{#if !signIn}
		<section
			transition:fly={{ duration: 700, x: -300, easing: linear }}
			class="grid h-110 w-[52%] grid-cols-4 overflow-hidden rounded shadow-2xl shadow-black"
		>
			<!-- left  -->
			<div
				class="col-span-2 flex flex-col justify-center rounded-sm rounded-l-none rounded-r-none border-transparent bg-orange-500 text-center text-white shadow-2xl"
			>
				<h1 class="text-[2em] font-semibold">Welcome Back!</h1>
				<p class="p-8 text-sm font-medium">
					To keep connected with us please login with your personal info
				</p>
				<button
					on:click={toggle()}
					class="mx-auto w-fit rounded-full bg-white px-8 py-2 text-sm font-semibold text-orange-400"
					>SIGN IN
				</button>
			</div>
			<!-- right -->
			<div
				class=" col-span-2 flex flex-col items-center justify-start gap-4 rounded-sm border border-transparent bg-white pt-15"
			>
				<h1 class="block font-sans text-[2rem] font-bold">Create Account</h1>
				<!-- icons -->
				<div class=" flex gap-3">
					<span class="size-8 rounded-full border border-[#DDDDDD] p-4"></span>
					<span class="size-8 rounded-full border border-[#DDDDDD] p-4"></span>
					<span class="size-8 rounded-full border border-[#DDDDDD] p-4"></span>
				</div>
				<p class="text-sm">or use your email for registration</p>

				<form action="#" class="space-y-3">
					<input
						type="text"
						placeholder="Name"
						class="bg-[#eee] px-5 py-2 text-sm placeholder-[#333]"
						min="2"
					/><br />
					<input
						type="email"
						placeholder="Email"
						class="bg-[#eee] px-5 py-2 text-sm placeholder-[#333]"
					/><br />
					<input
						type="password"
						placeholder="Password"
						class="bg-[#eee] px-5 py-2 text-sm placeholder-[#333]"
					/>
				</form>

				<!-- sign In -->
				<button class="rounded-full bg-orange-500 px-10 py-2 text-sm font-semibold text-white"
					>SIGN UP</button
				>
			</div>
		</section>
	{/if}
</main>

<!-- style -->
<style></style>
