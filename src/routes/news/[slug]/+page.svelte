<script lang="ts">
	import type { PageData } from './$types';
	import BackButton from '$lib/components/BackButton.svelte';
	import Footer from '$lib/components/Footer.svelte';
	let { data }: { data: PageData } = $props();
</script>

<svelte:head>
	<title>{data.title}</title>
	<meta name="description" content={data.subtitle} />
</svelte:head>

<section class="mx-auto max-w-4xl px-4 py-10 sm:px-6 lg:px-8">
	<div
		class="
    ml-0 pt-10
    pb-10
    sm:-ml-4
    md:-ml-2
    lg:-ml-16
    xl:-ml-32
    2xl:-ml-[178px]
  "
	>
		<BackButton />
	</div>

	<h1 class="mt-6 text-3xl leading-tight font-extrabold text-brand-text sm:text-4xl lg:text-5xl">
		{data.title}
	</h1>

	{#if data.mainImage}
		<div class="-mx-4 mt-8 sm:-mx-6 lg:-mx-8 xl:-mx-24 2xl:-mx-48">
			<img
				src={data.mainImage}
				alt={data.title}
				class="w-full rounded-lg object-cover shadow-md xl:h-[600px] 2xl:h-[600px]"
			/>
		</div>
	{/if}

	{#if data.subtitle}
		<p class="mt-8 text-[28px] leading-normal font-extrabold text-brand-text">
			{data.subtitle}
		</p>
	{/if}

	<div class="mt-8 space-y-6">
		{#each data.blocks as block, i (i)}
			{#if block.image}
				<div class="my-8">
					<img
						src={block.image}
						alt={data.subtitle}
						class="w-full rounded-lg object-cover shadow-md"
					/>
				</div>
			{/if}
			{#if block.text}
				<p class="text-base leading-relaxed text-brand-text sm:text-lg">
					{block.text}
				</p>
			{/if}
		{/each}
	</div>
</section>
<Footer />
