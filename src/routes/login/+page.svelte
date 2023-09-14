<script>
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

<div class=" bg-primary h-screen w-full flex justify-center items-center flex-col md:flex-row">
	<div class="">
		<img
			class="object-cover w-[20rem]"
			src="/Login_logo.svg"
			alt="Food logo for login/signup"
		/>
	</div>
	<form
		on:submit={sumbithandler}
		action="#"
		class=" bg-white space-y-8 min-w-[20rem] flex flex-col items-center p-4"
	>
		<!-- Email input with animation -->
		<span class="border flex h-14 items-center border-primary m-4 relative p-3 rounded-xl">
			<label
				for="email"
				class="{emailInputInFocus
					? 'absolute transition-slow top-[-0.65rem] text-sm text-gray-500'
					: 'absolute transition-slow top-[0.9rem] text-base'} px-2 bg-white"
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
		<span class="border flex h-14 items-center border-primary m-4 relative p-3 rounded-xl">
			<label
				for="password"
				class="{passwordInputInFocus
					? 'absolute transition-slow top-[-0.65rem] text-sm text-gray-500'
					: 'absolute transition-slow top-[0.9rem] text-base'} px-2 bg-white"
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
		<button
			class="bg-primary text-white py-2 px-4 rounded-full shadow-md transform translate-x-0 transition-transform hover:translate-x-2 hover:bg-gray-600"
		>
			Login
		</button>
	</form>
</div>

<style>
	.transition-slow {
		transition: all 0.2s ease-in-out; /* Adjust the duration and timing function as needed */
	}

img {
    pointer-events: none;
    -webkit-user-drag: none; 
}

*{
	user-select: none;
}

</style>
