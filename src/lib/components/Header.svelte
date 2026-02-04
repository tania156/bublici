<script>
	let isOpen = false;
	let isSubmenuOpen = false;
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
	<div class="relative 	headerContent min-[760px]:w-[75%] bg-[#3D0309] h-[100%] flex items-center max-[850px]:justify-center rounded-bl-[20px] w-full md:w-[75%] max-[760px]:flex-1 ">
		<div class=" h-[72px] flex items-center justify-end  gap-[16px] max-[1385px]:ml-[50px] xl:ml-[189px] max-[850px]:hidden whitespace-nowrap ">
			<a class="text-white text-[14px] max-[980px]:text-[12px] w-auto cursor-pointer hover:text-gray-300 transition-colors" href="#">
				Фаховий коледж
			</a>
			<a class="text-white text-[14px] max-[980px]:text-[12px] cursor-pointer hover:text-gray-300 transition-colors" href="#">
				діяльність
			</a>
			<a class="text-white text-[14px] max-[980px]:text-[12px] cursor-pointer hover:text-gray-300 transition-colors" href="#">
				студентство
			</a>
			<a class="text-white text-[14px] max-[980px]:text-[12px] cursor-pointer hover:text-gray-300 transition-colors" href="#">
				прес центр
			</a>
			<a class="text-white text-[14px] max-[980px]:text-[12px] cursor-pointer hover:text-gray-300 transition-colors" href="#">
				вступнику
			</a>

	</div>

		<div class=" max-[500px]:ml-[5px] w-auto sm:w-[176px]  h-[24px] flex justify-between bg-[#3D0309] max-[1385px]:ml-[50px] max-[935px]:ml-[20px]  min-[1400px]:ml-[189px] max-[1400px]:ml-[80px] mr-[5px] ml-[5px] sm:mr-[30px] ">
			<div class="flex gap-x-3 max-[1250px]:ml-[10px] ">
				<button class="text-white text-[14px] font-bold hover:opacity-80 transition-opacity max-[490px]:hidden">
					UA
				</button>

				<button class="text-white/40 text-[14px] font-normal hover:text-white/80 transition-colors  max-[490px]:mr-[10px]">
					EN
				</button>
			</div>
			<div class="flex">
				<button class=" min-[480px]:ml-[15px] hover:opacity-80 transition-opacity">
					<img alt="search" class="w-5 h-5 cursor-pointer" src="/img/lupa.svg">
					<path d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" stroke-linecap="round" stroke-linejoin="round"
								stroke-width="2" />

				</button>
				<img alt="menu" class=" ml-[3px] w-6 h-6 cursor-pointer " on:click={() => isOpen = true} src="/img/burger.svg">

				</div>
			</div>
		</div>
</header>
{#if isOpen}
	<div
		class="fixed top-0 left-0 z-[200]
           w-full h-[72px]
           bg-[#3D0309]
           flex items-center justify-between
           px-4"
	>
		<!-- ЛОГО + ТЕКСТ -->
		<div class="flex items-center gap-3">
			<img src="/img/logo.svg" class="h-8" alt="logo">

			<div class="w-[140px] h-[20px] ml-auto flex flex-col items-center justify-center">
				<h3 class="text-[8px] font-[700] text-white">Фаховий коледж технологій,
					бізнесу та права </h3>
				<p class="text-[6px] font-[400] text-white">Волинського Національного
					Університету Імені Лесі Українки</p>
			</div>
		</div>

		<!-- ХРЕСТИК -->
		<button
			class="text-white text-2xl"
			on:click={() => isOpen = false}
		>
			✕
		</button>
	</div>
{/if}
<div
	class="fixed left-0 z-[150]
         top-[72px]
         bg-[#3D0309]
         text-white
         w-[342px]
         max-h-[calc(100vh-72px)]
         overflow-y-auto
         transition-transform duration-300
         {isOpen ? 'translate-x-0' : '-translate-x-full'}"
>
	<!-- тут твій nav з пунктами -->
	<nav
		class="flex flex-col gap-8 p-4
           overflow-y-auto
           max-h-[calc(100vh-72px)]
           font-[Manrope]"
	>

		<!-- Фаховий коледж -->
		<button
			class="flex items-center justify-between
             text-[16px] leading-[24px] font-medium h-[48px]"
			on:click={() => isSubmenuOpen = !isSubmenuOpen}
		>
			<span>Фаховий Коледж</span>

			<span
				class="transition-transform duration-200
               {isSubmenuOpen ? 'rotate-180' : ''}"
			>
        {@html `
        <svg viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2"
             stroke-linecap="round" stroke-linejoin="round"
             class="w-4 h-4">
          <polyline points="6 9 12 15 18 9" />
        </svg>
        `}
      </span>
		</button>

		{#if isSubmenuOpen}
			<div class="flex flex-col gap-4">

				{#each [
					'Місія, цілі, документи',
					'Структура управління',
					'Колегіальні органи управління',
					'Громадські організації',
					'Кадри та вакансії',
					'Публічна інформація',
					'Профілактика корупції та конфлікту інтересів'
				] as item}
					<button
						class="flex items-center justify-between
                   text-[14px] h-[32px] pl-4
                   hover:opacity-80 transition-opacity"
					>
						<span>{item}</span>

						{@html `
            <svg viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2"
                 stroke-linecap="round" stroke-linejoin="round"
                 class="w-4 h-4 opacity-80">
              <polyline points="9 18 15 12 9 6" />
            </svg>
            `}
					</button>
				{/each}

			</div>
		{/if}

		<!-- Інші розділи -->
		{#each ['Діяльність', 'Студентство', 'Прес Центр', 'Вступнику'] as section}
			<button
				class="flex items-center justify-between
               text-[16px] h-[48px] font-medium
               hover:opacity-80 transition-opacity"
			>
				<span>{section}</span>

				{@html `
        <svg viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2"
             stroke-linecap="round" stroke-linejoin="round"
             class="w-4 h-4 opacity-80">
          <polyline points="9 18 15 12 9 6" />
        </svg>
        `}
			</button>
		{/each}

	</nav>
</div>
<style>
	.headerContent::after {content: '';
      position: absolute;
      left: -40px; /* Зсуваємо вліво на ширину кута */
      top: 0px;
      width: 40px;
      height: 40px;
      background: transparent; /* Фон прозорий */
      border-top-right-radius: 20px; /* Заокруглюємо протилежний кут */
      box-shadow: 20px 0px 0px 0 #3D0309; /* Тінь заповнює простір кольором блоку */
	}
	.headerContent::before {
			content: '';
      position: absolute;
      right: 16px; /* Зсуваємо вліво на ширину кута */
      bottom: -40px;
      width: 40px;
      height: 40px;
      background: transparent; /* Фон прозорий */
      border-top-right-radius: 20px; /* Заокруглюємо протилежний кут */
      box-shadow: 20px 0px 0px 0 #3D0309; /* Тінь заповнює простір кольором блоку */

	}
</style>
