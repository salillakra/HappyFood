<script>
	import '../../Utils/CSS/LoginButton.css'
	let emailInputInFocus = false;
	let passwordInputInFocus = false;

	//email and passoword bindings
	let password = '';
	let email = '';

	console.log(password, email);

	// Function to handle email input focus
	function handleEmailInputFocus() {
		emailInputInFocus = true;
	}

	// Function to handle email input blur
	function handleEmailInputBlur(event) {
		if (event.target.value.length == 0) emailInputInFocus = false;
	}

	// Function to handle password input focus
	function handlePasswordInputFocus() {
		passwordInputInFocus = true;
	}

	// Function to handle password input blur
	function handlePasswordInputBlur(event) {
		if (event.target.value.length == 0) passwordInputInFocus = false;
	}

	const sumbithandler = () => {
		console.log(password, email);
	};
</script>

<section class=" bg-primary h-screen w-full flex justify-center items-center ">
	<div class="login-container flex flex-col md:flex-row ">
	<div class="">
		<img
			class="object-cover w-80 lg:w-[30rem]"
			src="/Login_logo.svg"
			alt="Food logo for login/signup"
		/>
	</div>
	<form
		on:submit={sumbithandler}
		action="#"
		class="  bg-secondary rounded-lg space-y-8 md:w-96 flex flex-col items-center p-4"
	>
		<!-- Email input with animation -->
		<span class=" w-full md:w-5/6 mt-12 border flex h-14 items-center border-primary m-4 relative p-3 rounded-xl">
			<label
				for="email"
				class="{emailInputInFocus
					? 'absolute transition-slow top-[-0.65rem] text-sm text-teal-300'
					: 'absolute transition-slow top-[0.9rem] text-base'} px-2 bg-secondary"
			>
				Enter Your Email
			</label>
			<input
				bind:value={email}
				type="email"
				name="email"
				class="bg-transparent w-full transition-slow outline-none px-2 z-10 py-1"
				on:focus={handleEmailInputFocus}
				on:blur={handleEmailInputBlur}
			/>
		</span>

		<!-- Password input with animation -->
		<span class="border w-full md:w-5/6 flex h-14 items-center border-primary m-4 relative p-3 rounded-xl">
			<label
				for="password"
				class="{passwordInputInFocus
					? 'absolute transition-slow top-[-0.65rem] text-sm text-teal-300'
					: 'absolute transition-slow top-[0.9rem] text-base'} px-2 bg-secondary"
			>
				Enter Your Password
			</label>
			<input
				bind:value={password}
				type="password"
				name="password"
				class="bg-transparent w-full transition-slow outline-none px-2 z-10 py-1"
				on:focus={handlePasswordInputFocus}
				on:blur={handlePasswordInputBlur}
			/>
		</span>

		<!--  login button  -->
  		<button type="submit" class="button">Login</button>
	</form>
	</div>
</section>

<style>
	.transition-slow {
		transition: all 0.2s ease-in-out; /* Adjust the duration and timing function as needed */
	}

img {
    pointer-events: none;
    -webkit-user-drag: none; 
}

*{
	@apply text-white;
	user-select: none;
}

</style>
