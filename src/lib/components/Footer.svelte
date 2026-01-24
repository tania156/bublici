<script lang="ts">
	import { resolve } from '$app/paths';

	const mainLinks = [
		{ label: 'Фаховий Коледж', href: '/college' },
		{ label: 'Діяльність', href: '/activity' },
		{ label: 'Студентство', href: '/students' }
	];
	const additionalLinks = [
		{ label: 'Прес Центр', href: '/press' },
		{ label: 'Вступнику', href: '/admission' }
	];
</script>

<footer class="bg-brand-burgundy py-12 text-white">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div
			class="space-y-5 pl-4 md:grid md:grid-cols-[auto_auto_auto_auto] md:gap-8 md:space-y-0 lg:gap-16 xl:gap-32"
		>
			<!-- Логотип -->
			<div class="-ml-3 flex items-start gap-3">
				<img
					src="/img/logos1.svg"
					alt="Логотип Фахового Коледжу Технологій, Бізнесу та Права"
					class="-mt-4 h-24 w-24 shrink-0 object-contain min-[438px]:h-28 min-[438px]:w-28 sm:h-28 sm:w-28 md:h-24 md:w-24 lg:h-26 lg:w-26"
					width="80"
					height="80"
					loading="lazy"
				/>
				<div
					class="text-xs leading-snug uppercase opacity-90 min-[438px]:text-[11px] sm:text-[11px] md:text-[10px]"
				>
					<p class="font-semibold">
						Фаховий коледж технологій,<br />
						бізнесу та права
					</p>
					<p class="mt-1 opacity-80">
						Волинського національного<br />
						університету імені Лесі Українки
					</p>
				</div>
			</div>

			<!-- Навігація -->
			<nav class="flex flex-col gap-5" aria-label="Основна навігація">
				{#each mainLinks as link (link.href)}
					<a
						href={resolve(link.href)}
						class="text-xl font-medium min-[438px]:text-2xl sm:text-xl md:text-lg"
					>
						{link.label}
					</a>
				{/each}
			</nav>

			<nav class="flex flex-col gap-5" aria-label="Додаткова навігація">
				{#each additionalLinks as link (link.href)}
					<a
						href={resolve(link.href)}
						class="text-xl font-medium min-[438px]:text-2xl sm:text-xl md:text-lg"
					>
						{link.label}
					</a>
				{/each}
			</nav>

			<!-- Контакти -->
			<address class="mt-8 text-[#D7D7D7] not-italic md:mt-0">
				<h3
					class="mb-6 text-xl font-bold text-white min-[438px]:text-2xl sm:text-xl md:mb-3 md:text-lg"
				>
					Контакти
				</h3>
				<div class="space-y-1 text-xl min-[438px]:text-2xl sm:text-xl md:text-base">
					<p>м. Луцьк,</p>
					<p>проспект Волі, 51</p>
					<a href="mailto:pctbl.vnu@gmail.com" class="mt-6 block md:mt-4"> pctbl.vnu@gmail.com </a>
				</div>
			</address>
		</div>
	</div>
</footer>
