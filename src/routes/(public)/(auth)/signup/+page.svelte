<script lang="ts">
	import { enhance } from '$app/forms';

	let email: string;

	// const submitForm = () => {

	// // loadingState.set(true)
	// return async ({ result, update }: any) => {
	//   // loadingState.set(false)

	//   if (result.type === 'failure') {
	//     errors = result.data.errors

	//     toast.error(result.data.message, {
	//       duration: 5000,
	//       style: 'margin-top: 4rem',
	//     })
	//     return await applyAction(result)
	//   }
	//   errors = []
	//   toast.success('Registration succeed!', {
	//     duration: 5000,
	//     style: 'margin-top: 4rem',
	//   })
	//   update()
	// }
	// }
</script>

<svelte:head>
	<title>Sign up - P'tits Plats</title>
	<meta name="description" content="Sign up to access your account" />
</svelte:head>

<div class="w-full bg-white rounded-lg shadow md:mt-0 sm:max-w-md xl:p-0">
	<div class="p-6 space-y-4 md:space-y-6 sm:p-8">
		<h1 class="text-xl font-bold leading-tight tracking-tight text-gray-900 md:text-2xl">
			Créer un compte
		</h1>

		<!-- {#if form?.credentials}
        <p class="error">You have entered the wrong credentials.</p>
      {/if} -->

		<form method="post" class="space-y-4 md:space-y-6" action="?/signUp" use:enhance novalidate>
			<div>
				<label for="email" class="block mb-2 text-sm font-medium text-gray-900">Votre Email</label>
				<input
					bind:value={email}
					type="email"
					name="email"
					id="email"
					class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5"
					placeholder="name@company.com"
					required
				/>
				<!-- {#if errors?.email}
            <div class="text-red-500">{errors?.email[0]}</div>
          {/if} -->
			</div>
			<div>
				<label for="password" class="block mb-2 text-sm font-medium text-gray-900"
					>Mot de Passe</label
				>
				<input
					type="password"
					name="password"
					id="password"
					placeholder="••••••••"
					class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5"
					required
				/>
				<!-- {#if errors?.password}
            <div class="text-red-500">{errors?.password[0]}</div>
          {/if} -->
			</div>
			<div>
				<label for="confirmPassword" class="block mb-2 text-sm font-medium text-gray-900"
					>Confirmez le Mot de Passe</label
				>
				<input
					type="password"
					name="confirmPassword"
					id="confirmPassword"
					placeholder="••••••••"
					class="bg-gray-50 border border-gray-300 text-gray-900 sm:text-sm rounded-lg focus:ring-primary-600 focus:border-primary-600 block w-full p-2.5"
					required
				/>
				<!-- {#if errors?.confirmPassword}
            <div class="text-red-500">{errors?.confirmPassword[0]}</div>
          {/if} -->
				<!-- {#if errors?.passwordNotMatching == true}
            <div class="text-red-500">Both passwords have to match</div>
          {/if} -->
			</div>
			<div class="flex items-end justify-between" />
			<button
				type="submit"
				class="outline outline-2 outline-orange-300 hover:outline-4 shadow-md active:shadow-none font-medium rounded-lg text-sm w-full px-5 py-2.5 text-center duration-100"
				>Créer mon Compte</button
			>
			<p class="text-sm font-light text-gray-500">
				Vous avez déjà un compte? <a
					href="/signin"
					class="font-medium text-primary-600 hover:underline">Se Connecter</a
				>
			</p>
		</form>
	</div>
</div>
