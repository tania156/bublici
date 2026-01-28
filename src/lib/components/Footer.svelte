<script lang="ts">
	import { resolve } from '$app/paths';

	const links = [
		{ label: 'Фаховий Коледж', href: '/college' },
		{ label: 'Діяльність', href: '/activity' },
		{ label: 'Студентство', href: '/students' },
		{ label: 'Прес Центр', href: '/press' },
		{ label: 'Вступнику', href: '/admission' }
	];
</script>

<footer class="bg-brand-burgundy py-12 text-white">
	<div class="mx-auto max-w-7xl px-4 sm:px-6 lg:px-8">
		<div class="grid gap-5 pl-4 md:grid-cols-[auto_auto_auto] md:gap-8 lg:gap-16 xl:gap-32">
			<!-- Логотип -->
			<div class="-ml-3 flex items-start gap-3">
				<img
					src="/img/logos1.svg"
					alt="Логотип Фахового Коледжу Технологій, Бізнесу та Права"
					class="-mt-4 size-24 shrink-0 object-contain min-[438px]:size-28 sm:size-28 md:size-24 lg:size-26"
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
					<p class="mt-1 font-normal opacity-80">
						Волинського національного<br />
						університету імені Лесі Українки
					</p>
				</div>
			</div>

			<!-- Навігація -->
			<nav
				class="grid grid-rows-none gap-5 md:grid-flow-col md:grid-rows-3 md:gap-x-8 lg:gap-x-16 xl:gap-x-32"
				aria-label="Основна навігація"
			>
				{#each links as link (link.href)}
					<a
						href={resolve(link.href)}
						class="group relative inline-block text-xl font-medium duration-300 min-[438px]:text-2xl sm:text-xl md:text-lg md:transition-colors md:hover:text-red-200"
					>
						{link.label}
						<span
							class="absolute bottom-[-2px] left-0 h-[2px] w-0 bg-red-200 transition-[width] duration-300 md:group-hover:w-full"
						></span>
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
				<div class="space-y-1 text-xl font-normal min-[438px]:text-2xl sm:text-xl md:text-base">
					<p>м. Луцьк,</p>
					<p>проспект Волі, 51</p>
					<a href="mailto:pctbl.vnu@gmail.com" class="mt-6 inline-block md:mt-4">
						pctbl.vnu@gmail.com
					</a>
				</div>
			</address>
		</div>
	</div>
</footer>
