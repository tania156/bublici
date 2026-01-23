<script lang="ts">
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

<footer class="bg-[#3D0309] text-white py-12">
	<div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
		<div class="space-y-5 md:grid md:grid-cols-[auto_auto_auto_auto] md:gap-8 lg:gap-16 xl:gap-32 md:space-y-0 pl-4">
			<!-- Логотип -->
			<div class="flex items-start gap-3 -ml-3">
				<img
					src="/img/logos1.svg"
					alt="Логотип Фахового Коледжу Технологій, Бізнесу та Права"
					class="-mt-4 h-24 w-24 min-[438px]:h-28 min-[438px]:w-28 sm:h-28 sm:w-28 md:h-24 md:w-24 lg:h-26 lg:w-26 shrink-0 object-contain"
					width="80"
					height="80"
					loading="lazy"
				/>
				<div class="text-xs min-[438px]:text-[11px] sm:text-[11px] md:text-[10px] leading-snug uppercase opacity-90">
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
					<a href={link.href} class="text-xl min-[438px]:text-2xl sm:text-xl md:text-lg font-medium">
						{link.label}
					</a>
				{/each}
			</nav>
			
			<nav class="flex flex-col gap-5" aria-label="Додаткова навігація">
				{#each additionalLinks as link (link.href)}
					<a href={link.href} class="text-xl min-[438px]:text-2xl sm:text-xl md:text-lg font-medium">
						{link.label}
					</a>
				{/each}
			</nav>
			
			<!-- Контакти -->
			<address class="not-italic text-[#D7D7D7] md:mt-0 mt-8">
				<h3 class="text-xl min-[438px]:text-2xl sm:text-xl md:text-lg font-bold mb-6 md:mb-3 text-white">Контакти</h3>
				<div class="space-y-1 text-xl min-[438px]:text-2xl sm:text-xl md:text-base">
					<p>м. Луцьк,</p>
					<p>проспект Волі, 51</p>
					<a href="mailto:pctbl.vnu@gmail.com" class="block mt-6 md:mt-4">
						pctbl.vnu@gmail.com
					</a>
				</div>
			</address>
		</div>
	</div>
</footer>
