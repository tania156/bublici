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

<header class="w-full h-[72px] flex  items-center relative z-50 {isOpen ? 'hidden' : 'flex'}">
	<div class="min-[760px]:w-[30%] h-[100%] flex items-end justify-end mr-[24px] max-w-[760px]:w-[220px] ">
		<div class="mb-[5px] h-[48px] w-[204px]  rounded-[10px] flex items-center px-[8px] py-[4px] bg-[#3D0309] max-[1000px]:ml-[30px] max-[400px]:ml-[8px]">
			<img alt="Логотип Фахового коледжу " src="/img/logo.svg">
			<div class="w-[140px] h-[20px] ml-auto flex flex-col items-center justify-center">
				<h3 class="text-[8px] font-[700] text-white">Фаховий коледж технологій,
					бізнесу та права </h3>
				<p class="text-[6px] font-[400] text-white">Волинського Національного
					Університету Імені Лесі Українки</p>
			</div>

		</div>
	</div>
	<div
		class="relative  headerContent min-[760px]:w-[75%] bg-[#3D0309] h-[100%] flex items-center max-[850px]:justify-center rounded-bl-[20px] w-full md:w-[75%] max-[760px]:flex-1 ">
		<div class=" h-[72px] flex items-center justify-end  gap-[16px] max-[1385px]:ml-[50px] xl:ml-[189px] max-[850px]:hidden whitespace-nowrap ">
			<button
				class="text-white text-[14px] max-[980px]:text-[12px] w-auto cursor-pointer hover:text-gray-300 transition-colors font-[Manrope]"
				onclick={() => openMobileMenuAt('activity')}>
				ФАХОВИЙ КОЛЕДЖ
			</button>
			<button
				class="text-white text-[14px] max-[980px]:text-[12px] w-auto cursor-pointer hover:text-gray-300 transition-colors font-[Manrope]"
				onclick={() => openMobileMenuAt('activity')}>
				ДІЯЛЬНІСТЬ
			</button>
			<button
				class="text-white text-[14px] max-[980px]:text-[12px] w-auto cursor-pointer hover:text-gray-300 transition-colors font-[Manrope]"
				onclick={() => openMobileMenuAt('activity')}>
				СТУДЕНТСТВО
			</button>
			<button
				class="text-white text-[14px] max-[980px]:text-[12px] w-auto cursor-pointer hover:text-gray-300 transition-colors font-[Manrope]"
				onclick={() => openMobileMenuAt('activity')}>
				ПРЕС ЦЕНТР
			</button>
			<button
				class="text-white text-[14px] max-[980px]:text-[12px] w-auto cursor-pointer hover:text-gray-300 transition-colors font-[Manrope]"
				onclick={() => openMobileMenuAt('activity')}>
				ВСТУПНИКУ
			</button>

		</div>
		<div class="w-auto h-[24px] max-[500px]:ml-[5px] sm:w-[176px] flex justify-between bg-[#3D0309] max-[1385px]:ml-[50px] max-[935px]:ml-[20px]  min-[1400px]:ml-[189px] max-[1400px]:ml-[80px] mr-[5px] ml-[5px] sm:mr-[30px] ">
			<div class="flex gap-x-3 max-[1250px]:ml-[10px] ">
				<button class="text-white text-[14px] font-bold hover:opacity-80 transition-opacity max-[490px]:hidden">
					UA
				</button>

				<button class="text-white/40 text-[14px] font-normal hover:text-white/80 transition-colors  max-[490px]:mr-[10px]">
					EN
				</button>
			</div>
			<div class="flex">
				<button class=" min-[480px]:ml-[15px] hover:opacity-80 transition-opacity shrink-0 mr-[15px] max-[1050px]:mr-0">
					<img alt="search" class="w-5 h-5 cursor-pointer  shrink-0" src="/img/lupa.svg">
					<path d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" stroke-linecap="round" stroke-linejoin="round"
								stroke-width="2" />
				</button>
				<button type="button" onclick={() =>isOpen = true} class="bg-transparent border-none p-0 flex items-center justify-center" aria-label="Відкрити меню">
				<img alt="open menu" class="w-6 h-6 cursor-pointer shrink-0" src="/img/burger.svg">
				</button>
			</div>
		</div>
	</div>
</header>
{#if isOpen}
	<div class="absolute top-0 left-0 z-[200] w-[100%] h-[100%] pt-[10px] bg-[#3D0309] flex flex-col">
		<div class="flex justify-between w-full px-[20px] items-center">
			<div class=" h-[48px] w-[189px]  rounded-[10px] flex items-center bg-[#3D0309]">
				<img alt="Логотип Фахового коледжу " src="/img/logo.svg">
				<div class="w-[140px] h-[20px] ml-auto flex flex-col items-center justify-center">
					<h3 class="text-[8px] font-[700] text-white">Фаховий коледж технологій,
						бізнесу та права </h3>
					<p class="text-[6px] font-[400] text-white">Волинського Національного
						Університету Імені Лесі Українки</p>
				</div>
			</div>
			<button type="button" onclick={() => isOpen = false} class="bg-transparent border-none p-0 cursor-pointer ">
				<img src="/img/x.svg" alt="Закрити меню" class="w-6 h-6" />
			</button>
		</div>
		<div class="w-full h-full bg-[#3D0309] p-[24px] text-white overflow-y-auto">

			{#each menuItems as item (item.id)}
				<div class="mb-4 pb-2">
					<div
						class="flex justify-between items-center cursor-pointer py-2"
					>
						<h2 class="text-[18px] font-medium uppercase tracking-wide">
							{item.label}
						</h2>

						<button
							aria-label="Відкрити меню "
							type="button"
							class="transition-transform duration-300"
							style="transform: rotate({openSection === item.id ? '180deg' : '0deg'})"
							onclick={() => toggleSection(item.id)} >
							<svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
								<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7" />
							</svg>
					</button>
					</div>

					{#if openSection === item.id}
						<ul
							transition:slide={{ duration: 300 }}
							class="mt-2 ml-4 flex flex-col gap-3 pl-4"
						>
							{#if item.children}
								{#each item.children as child (child.id)}
									<li>
										<a href="#{child.id}"
											 class="flex justify-between items-center text-white/70 hover:text-white transition-colors text-[16px] py-1">

											<span>{child.label}</span>
											<svg class="w-4 h-4 opacity-50" fill="none" stroke="currentColor" viewBox="0 0 24 24">
												<path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M9 5l7 7-7 7" />
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
        box-shadow: 20px 0 0 0 #3D0309;
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
        box-shadow: 20px 0 0 0 #3D0309;
		}
</style>
