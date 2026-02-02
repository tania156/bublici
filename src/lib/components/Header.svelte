<script>
	let isOpen = false;

</script>

<header class="w-full h-[72px] flex  items-center relative z-50 ">
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

		<div class="w-[176px]  h-[24px] flex justify-between bg-[#3D0309] max-[1385px]:ml-[50px] max-[935px]:ml-[20px]  min-[1400px]:ml-[189px] max-[1400px]:ml-[80px] mr-[30px]">
			<div class="flex gap-x-3 max-[1250px]:ml-[10px]">
				<button class="text-white text-[14px] font-bold hover:opacity-80 transition-opacity">
					UA
				</button>

				<button class="text-white/40 text-[14px] font-normal hover:text-white/80 transition-colors">
					EN
				</button>
			</div>
			<div class="flex">
				<button class="text-white hover:opacity-80 transition-opacity">
					<img alt="search" class="w-5 h-5 cursor-pointer" src="/img/lupa.svg">
					<path d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z" stroke-linecap="round" stroke-linejoin="round"
								stroke-width="2" />

				</button>
				<img alt="menu" class=" ml-[20px] w-6 h-6 cursor-pointer " on:click={() => isOpen = true} src="/img/burger.svg">

				</div>
			</div>
		</div>
	<div class="{isOpen ? 'flex' : 'hidden'} absolute top-0 left-0 z-[100] w-full h-full bg-white flex-col p-4">
		<!--					<div class="flex">-->
		<!--						<img alt="menu" class="w-15 h-15  " on:click={() => isOpen = false} src="/img/burger.svg"></div>-->

		<ul class=" left-0 top-[100%] md:flex md:items-center z-[-1] md:z-auto md:static absolute bg-[#3D0309] w-full md:w-auto md:py-0 py-4 md:pl-0 pl-7">
			<li class="mx-4 my-6 md:my-0">
				<a href="#" class="text-xl hover:text-gray-600 duration-500 text-white">Фаховий Коледж</a>
			</li>
			<li class="mx-4 my-6 md:my-0">
				<a href="#" class="text-xl hover:text-gray-600 duration-500 text-white">Діяльність</a>
			</li>
			<li class="mx-4 my-6 md:my-0">
				<a href="#" class="text-xl hover:text-gray-600 duration-500 text-white">Студенство</a>
			</li>
			<li class="mx-4 my-6 md:my-0">
				<a href="#" class="text-xl hover:text-gray-600 duration-500 text-white">Прес Центр</a>
			</li>
			<li class="mx-4 my-6 md:my-0">
				<a href="#" class="text-xl hover:text-gray-600 duration-500 text-white">Вступнику</a>
			</li>
		</ul>
	</div>
</header>
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
