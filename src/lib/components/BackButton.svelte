<button
	onclick={() => history.back()}
	class="
    group flex h-12
    w-12 cursor-pointer
    items-center
    justify-center rounded-full
    border-2
    border-brand-bg
    bg-white
    transition-all duration-200
    hover:bg-brand-bg
	hover:text-white
  "
	aria-label="Повернутися назад"
>
	<svg
		xmlns="http://www.w3.org/2000/svg"
		fill="none"
		viewBox="0 0 24 24"
		stroke-width="2"
		stroke="currentColor"
		class="h-6 w-6 text-brand-text transition-colors group-hover:text-white"
	>
		<path stroke-linecap="round" stroke-linejoin="round" d="M10.5 19.5L3 12m0 0l7.5-7.5M3 12h18" />
	</svg>
</button>
