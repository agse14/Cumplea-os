<script lang="ts">
	import { onMount } from 'svelte';

	let mounted = $state(false);

	onMount(() => {
		mounted = true;
	});
</script>

<svelte:head>
	<title>¡Ava cumple 9 años! 🎉</title>
	<meta name="description" content="Invitación al cumpleaños de Ava - 14 de julio de 2026" />
	<meta property="og:title" content="¡Ava cumple 9 años! 🎉" />
	<meta property="og:description" content="Estás cordialmente invitado a celebrar los 9 años de Ava" />
	<meta property="og:type" content="website" />
	<meta name="twitter:card" content="summary_large_image" />
</svelte:head>

<!-- Animated background -->
<div
	class="fixed inset-0 -z-10"
	style="background: linear-gradient(135deg, #fdf2f8 0%, #ede9fe 25%, #fef3c7 50%, #ede9fe 75%, #fce7f3 100%); background-size: 400% 400%; animation: gradientShift 10s ease infinite;"
></div>

<!-- Confetti -->
<div class="fixed inset-0 pointer-events-none overflow-hidden -z-10">
	{#each Array(20) as _, i}
		<div
			class="confetti"
			style="left: {Math.random() * 100}%; animation-delay: {Math.random() * 3}s; animation-duration: {3 + Math.random() * 3}s; background: {['#ec4899', '#a855f7', '#facc15', '#14b8a6', '#f97316', '#ef4444'][i % 6]}; width: {6 + Math.random() * 8}px; height: {6 + Math.random() * 6}px; border-radius: {Math.random() > 0.5 ? '50%' : '2px'};"
		></div>
	{/each}
</div>

<!-- Balloons -->
<div class="fixed inset-0 pointer-events-none overflow-hidden -z-10">
	{#each Array(5) as _, i}
		<div
			class="balloon"
			style="left: {10 + i * 18}%; animation-delay: {i * 0.8}s; animation-duration: {6 + i * 0.5}s; font-size: {2 + Math.random() * 1.5}rem;"
		>
			🎈
		</div>
	{/each}
</div>

<!-- Stars -->
<div class="fixed inset-0 pointer-events-none -z-10">
	{#each [{ top: '8%', left: '10%', delay: '0s' }, { top: '15%', left: '85%', delay: '0.5s' }, { top: '25%', left: '5%', delay: '1s' }, { top: '10%', left: '75%', delay: '1.5s' }, { top: '30%', left: '88%', delay: '0.3s' }, { top: '20%', left: '30%', delay: '0.8s' }, { top: '35%', left: '15%', delay: '1.2s' }, { top: '5%', left: '50%', delay: '1.7s' }] as star}
		<span
			class="star"
			style="top: {star.top}; left: {star.left}; animation-delay: {star.delay};"
		>
			{['⭐', '✨', '🌟', '⭐', '✨', '🌟'][Math.floor(Math.random() * 6)]}
		</span>
	{/each}
</div>

<!-- Decorative blobs -->
<div class="fixed -top-20 -right-20 w-72 h-72 -z-10 opacity-30 rounded-full" style="background: radial-gradient(circle, #facc15 0%, transparent 70%);"></div>
<div class="fixed -bottom-20 -left-20 w-56 h-56 -z-10 opacity-30 rounded-full" style="background: radial-gradient(circle, #ec4899 0%, transparent 70%);"></div>
<div class="fixed top-1/2 -left-16 w-40 h-40 -z-10 opacity-20 rounded-full" style="background: radial-gradient(circle, #a855f7 0%, transparent 70%);"></div>

<!-- Main card -->
<div class="min-h-screen flex items-center justify-center p-4">
	<div
		class="w-full max-w-md bg-white/80 backdrop-blur-xl border border-white/60 rounded-3xl shadow-2xl p-8 sm:p-12 text-center relative transition-all duration-500"
		class:opacity-0={!mounted}
		class:opacity-100={mounted}
		class:translate-y-4={!mounted}
		class:translate-y-0={mounted}
		style="box-shadow: 0 20px 60px rgba(236, 72, 153, 0.12), 0 8px 20px rgba(0,0,0,0.04);"
	>
		<!-- Big 9 -->
		<span class="block font-display text-8xl sm:text-9xl leading-none bg-gradient-to-r from-pink-500 via-purple-500 to-yellow-400 bg-clip-text text-transparent animate-pulse-scale">
			9
		</span>

		<h1 class="font-display text-3xl sm:text-4xl text-[#1e1b4b] mt-1">
			¡Ava cumple 9 años!
		</h1>

		<p class="text-base text-gray-400 mt-2 font-normal">
			Estás cordialmente invitado a celebrar con nosotros
		</p>

		<div class="h-px my-6 bg-gradient-to-r from-transparent via-pink-200 to-transparent"></div>

		<!-- Details -->
		<div class="flex flex-col gap-3 text-left">

			<div class="flex items-center gap-3 p-3.5 rounded-xl transition-all duration-200 hover:bg-pink-50/80 hover:translate-x-1" style="background: rgba(236, 72, 153, 0.04);">
				<span class="text-xl flex-shrink-0">📅</span>
				<div>
					<div class="text-xs text-gray-400 font-medium uppercase tracking-wide">Fecha</div>
					<div class="font-semibold text-[#1e1b4b]">14 de julio de 2026</div>
				</div>
			</div>

			<div class="flex items-center gap-3 p-3.5 rounded-xl transition-all duration-200 hover:bg-pink-50/80 hover:translate-x-1" style="background: rgba(236, 72, 153, 0.04);">
				<span class="text-xl flex-shrink-0">⏰</span>
				<div>
					<div class="text-xs text-gray-400 font-medium uppercase tracking-wide">Hora</div>
					<div class="font-semibold text-[#1e1b4b]">3:00 PM</div>
				</div>
			</div>

			<div class="flex items-center gap-3 p-3.5 rounded-xl transition-all duration-200 hover:bg-pink-50/80 hover:translate-x-1" style="background: rgba(236, 72, 153, 0.04);">
				<span class="text-xl flex-shrink-0">📍</span>
				<div>
					<div class="text-xs text-gray-400 font-medium uppercase tracking-wide">Lugar</div>
					<div class="font-semibold text-[#1e1b4b]">Bahia Grande #3721</div>
					<div class="text-sm text-gray-500">Col. Rincón de la Primavera</div>
				</div>
			</div>

		</div>

		<div class="h-px my-6 bg-gradient-to-r from-transparent via-pink-200 to-transparent"></div>

		<!-- RSVP -->
		<p class="text-sm text-gray-400 mb-4">
			¡Confirma tu asistencia!
		</p>

		<a
			href="https://wa.me/528116263034?text=¡Hola!%20Confirmo%20mi%20asistencia%20al%20cumpleaños%20de%20Ava%20🎉"
			target="_blank"
			rel="noopener noreferrer"
			class="btn-primary w-full gap-2"
		>
			<svg class="w-5 h-5" fill="currentColor" viewBox="0 0 24 24">
				<path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
			</svg>
			Confirmar por WhatsApp
		</a>

		<div class="mt-5">
			<a href="/" class="btn-secondary">
				← Regresar
			</a>
		</div>
	</div>
</div>

<style>
	@keyframes gradientShift {
		0% { background-position: 0% 50%; }
		50% { background-position: 100% 50%; }
		100% { background-position: 0% 50%; }
	}

	@keyframes confettiFall {
		0% { transform: translateY(-10px) rotate(0deg); opacity: 1; }
		100% { transform: translateY(100vh) rotate(720deg); opacity: 0; }
	}

	.confetti {
		position: absolute;
		top: -10px;
		animation: confettiFall linear infinite;
	}

	@keyframes floatBalloon {
		0% { transform: translateY(0) rotate(-5deg); }
		25% { transform: translateY(-20vh) rotate(5deg); }
		50% { transform: translateY(-40vh) rotate(-3deg); }
		75% { transform: translateY(-60vh) rotate(4deg); }
		100% { transform: translateY(-100vh) rotate(-2deg); }
	}

	.balloon {
		position: absolute;
		bottom: -60px;
		animation: floatBalloon ease-in-out infinite;
		opacity: 0.7;
	}

	@keyframes twinkle {
		0%, 100% { opacity: 0.2; transform: scale(0.8); }
		50% { opacity: 0.8; transform: scale(1.2); }
	}

	.star {
		position: absolute;
		font-size: 1.2rem;
		animation: twinkle 2s ease-in-out infinite;
	}

	@keyframes pulseScale {
		0%, 100% { transform: scale(1); }
		50% { transform: scale(1.08); }
	}

	.animate-pulse-scale {
		animation: pulseScale 2s ease-in-out infinite;
	}
</style>
