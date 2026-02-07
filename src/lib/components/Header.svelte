<script lang="ts">
	let isOpen = $state(false);
	import { slide } from 'svelte/transition';

	function openMobileMenuAt(sectionId: string) {
		isOpen = true;
		openSection = sectionId;
	}

	//  Спочатку я оголошую дочірній елемент
	interface ChildItem {
		id: string;
		label: string;
	}

	// Потім головний елемент
	interface MenuItem {
		id: string;
		label: string;
		children?: ChildItem[];
	}

	// Заповнюю масив
	const menuItems: MenuItem[] = [
		{
			id: 'college',
			label: 'Фаховий Коледж',
			children: [
				{ id: 'col-mission', label: 'Місія, цілі, документи' },
				{ id: 'col-structure', label: 'Структура управління' },
				{ id: 'col-collegiate', label: 'Колегіальні органи управління' },
				{ id: 'col-organizations', label: 'Громадські організації' },
				{ id: 'col-hr', label: 'Кадри та вакансії' },
				{ id: 'col-public-info', label: 'Публічна інформація' },
				{ id: 'col-anti-corruption', label: 'Профілактика корупції' }
			]
		}, // головне не забути тут кому
		{
			id: 'activity',
			label: 'Діяльність',
			children: [
				{ id: 'col-hr', label: 'Кадри та вакансії' },
				{ id: 'col-public-info', label: 'Публічна інформація' },
				{ id: 'col-anti-corruption', label: 'Профілактика корупції' }
			] //пізніше тут зміниться вміст
		},
		{
			id: 'students',
			label: 'Студентство',
			children: [
				{ id: 'col-hr', label: 'Кадри та вакансії' },
				{ id: 'col-public-info', label: 'Публічна інформація' },
				{ id: 'col-anti-corruption', label: 'Профілактика корупції' }
			]
		},
		{
			id: 'pres',
			label: 'Прес Центр',
			children: [
				{ id: 'col-hr', label: 'Кадри та вакансії' },
				{ id: 'col-public-info', label: 'Публічна інформація' },
				{ id: 'col-anti-corruption', label: 'Профілактика корупції' }
			]
		},
		{
			id: 'stud',
			label: 'Вступнику',
			children: [
				{ id: 'col-hr', label: 'Кадри та вакансії' },
				{ id: 'col-public-info', label: 'Публічна інформація' },
				{ id: 'col-anti-corruption', label: 'Профілактика корупції' }
			]
		}
	];

	let openSection = $state<string | null>(null);

	function toggleSection(id: string) {
		openSection = openSection === id ? null : id;
	}
</script>

<header class="relative z-50 flex h-[72px] w-full items-center {isOpen ? 'hidden' : 'flex'}">
	<div
		class="max-w-[760px]:w-[220px] mr-[24px] flex h-[100%] items-end justify-end min-[760px]:w-[30%]"
	>
		<div
			class="mb-[5px] flex h-[48px] w-[204px] items-center rounded-[10px] bg-[#3D0309] px-[8px] py-[4px] max-[1000px]:ml-[30px] max-[400px]:ml-[8px]"
		>
			<img alt="Логотип Фахового коледжу " src="/img/logo.svg" />
			<div class="ml-auto flex h-[20px] w-[140px] flex-col items-center justify-center">
				<h3 class="text-[8px] font-[700] text-white">
					Фаховий коледж технологій, бізнесу та права
				</h3>
				<p class="text-[6px] font-[400] text-white">
					Волинського Національного Університету Імені Лесі Українки
				</p>
			</div>
		</div>
	</div>
	<div
		class="headerContent relative flex h-[100%] w-full items-center rounded-bl-[20px] bg-[#3D0309] max-[850px]:justify-center max-[760px]:flex-1 min-[760px]:w-[75%] md:w-[75%]"
	>
		<div
			class=" flex h-[72px] items-center justify-end gap-[16px] whitespace-nowrap max-[1385px]:ml-[40px] max-[850px]:hidden xl:ml-[119px]"
		>
			<button
				class="w-auto cursor-pointer font-[Manrope] text-[14px] text-white transition-colors hover:text-gray-300 max-[1050px]:text-[10px]"
				onclick={() => openMobileMenuAt('activity')}
			>
				ФАХОВИЙ КОЛЕДЖ
			</button>
			<button
				class="w-auto cursor-pointer font-[Manrope] text-[14px] text-white transition-colors hover:text-gray-300 max-[1050px]:text-[10px]"
				onclick={() => openMobileMenuAt('activity')}
			>
				ДІЯЛЬНІСТЬ
			</button>
			<button
				class="w-auto cursor-pointer font-[Manrope] text-[14px] text-white transition-colors hover:text-gray-300 max-[1050px]:text-[10px]"
				onclick={() => openMobileMenuAt('activity')}
			>
				СТУДЕНТСТВО
			</button>
			<button
				class="w-auto cursor-pointer font-[Manrope] text-[14px] text-white transition-colors hover:text-gray-300 max-[1050px]:text-[10px]"
				onclick={() => openMobileMenuAt('activity')}
			>
				ПРЕС ЦЕНТР
			</button>
			<button
				class="w-auto cursor-pointer font-[Manrope] text-[14px] text-white transition-colors hover:text-gray-300 max-[1050px]:text-[10px]"
				onclick={() => openMobileMenuAt('activity')}
			>
				ВСТУПНИКУ
			</button>
		</div>
		<div class="flex-1 max-[850px]:hidden"></div>
		<div
			class="ml-[5px] flex h-[24px] justify-between bg-[#3D0309] max-[1385px]:ml-[30px] max-[935px]:ml-[5px] max-[500px]:ml-[5px] sm:mr-[15px] lg:w-[176px]"
		>
			<div class="flex gap-x-3 max-[1250px]:ml-[10px] xl:ml-[20px]">
				<button
					class="text-[14px] font-bold text-white transition-opacity hover:opacity-80 max-[490px]:hidden"
				>
					UA
				</button>

				<button
					class="text-[14px] font-normal text-white/40 transition-colors hover:text-white/80 max-[490px]:mr-[10px]"
				>
					EN
				</button>
			</div>
			<div class="flex">
				<button
					class="  mr-[15px] shrink-0 transition-opacity hover:opacity-80 min-[480px]:ml-[15px]"
				>
					<img alt="search" class="h-5 w-5 shrink-0 cursor-pointer" src="/img/lupa.svg" />
					<path
						d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"
						stroke-linecap="round"
						stroke-linejoin="round"
						stroke-width="2"
					/>
				</button>
				<button
					type="button"
					onclick={() => (isOpen = true)}
					class="flex items-center justify-center border-none bg-transparent p-0"
					aria-label="Відкрити меню"
				>
					<img alt="open menu" class="h-6 w-6 shrink-0 cursor-pointer" src="/img/burger.svg" />
				</button>
			</div>
		</div>
	</div>
</header>
{#if isOpen}
	<div class="absolute top-0 left-0 z-[200] flex h-[100%] w-[100%] flex-col bg-[#3D0309] pt-[10px]">
		<div class="flex w-full items-center justify-between px-[20px]">
			<div class=" flex h-[48px] w-[189px] items-center rounded-[10px] bg-[#3D0309]">
				<img alt="Логотип Фахового коледжу " src="/img/logo.svg" />
				<div class="ml-auto flex h-[20px] w-[140px] flex-col items-center justify-center">
					<h3 class="text-[8px] font-[700] text-white">
						Фаховий коледж технологій, бізнесу та права
					</h3>
					<p class="text-[6px] font-[400] text-white">
						Волинського Національного Університету Імені Лесі Українки
					</p>
				</div>
			</div>
			<button
				type="button"
				onclick={() => (isOpen = false)}
				class="cursor-pointer border-none bg-transparent p-0"
			>
				<img src="/img/x.svg" alt="Закрити меню" class="h-6 w-6" />
			</button>
		</div>
		<div class="h-full w-full overflow-y-auto bg-[#3D0309] p-[24px] text-white">
			{#each menuItems as item (item.id)}
				<div class="mb-4 pb-2">
					<div class="flex cursor-pointer items-center justify-between py-2">
						<h2 class="text-[18px] font-medium tracking-wide uppercase">
							{item.label}
						</h2>

						<button
							aria-label="Відкрити меню "
							type="button"
							class="transition-transform duration-300"
							style="transform: rotate({openSection === item.id ? '180deg' : '0deg'})"
							onclick={() => toggleSection(item.id)}
						>
							<svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
								<path
									stroke-linecap="round"
									stroke-linejoin="round"
									stroke-width="2"
									d="M19 9l-7 7-7-7"
								/>
							</svg>
						</button>
					</div>

					{#if openSection === item.id}
						<ul transition:slide={{ duration: 300 }} class="mt-2 ml-4 flex flex-col gap-3 pl-4">
							{#if item.children}
								{#each item.children as child (child.id)}
									<li>
										<a
											href="#{child.id}"
											class="flex items-center justify-between py-1 text-[16px] text-white/70 transition-colors hover:text-white"
										>
											<span>{child.label}</span>
											<svg
												class="h-4 w-4 opacity-50"
												fill="none"
												stroke="currentColor"
												viewBox="0 0 24 24"
											>
												<path
													stroke-linecap="round"
													stroke-linejoin="round"
													stroke-width="2"
													d="M9 5l7 7-7 7"
												/>
											</svg>
										</a>
									</li>
								{/each}
							{/if}
						</ul>
					{/if}
				</div>
			{/each}
		</div>
	</div>
{/if}

<style>
	.headerContent::after {
		content: '';
		position: absolute;
		left: -40px;
		top: 0;
		width: 40px;
		height: 40px;
		background: transparent;
		border-top-right-radius: 20px;
		box-shadow: 20px 0 0 0 #3d0309;
	}

	.headerContent::before {
		content: '';
		position: absolute;
		right: 16px;
		bottom: -40px;
		width: 40px;
		height: 40px;
		background: transparent;
		border-top-right-radius: 20px;
		box-shadow: 20px 0 0 0 #3d0309;
	}
</style>
