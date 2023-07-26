<template>
	<div class="select-items">
		<div class="select-items__flex">
			<div v-for="(item, id) in itemsLeft.checkItems" :key="id" class="select-items__item">
				{{ item }}
			</div>
		</div>
		<p class="select-items__counter">{{ itemsLeft.checkItems?.length ?? 0 }} / 6</p>
	</div>
</template>

<script>
	export default {
		name: "SelectItems",
		props: ["itemsLeft"],
	}
</script>

<style>
	.select-items {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
		border: 1px solid #000;
		padding: 10px;
		max-width: 342px;
		width: 100%;
	}

	.select-items__flex {
		display: flex;
		flex-wrap: wrap;
		margin-bottom: 10px;
		gap: 10px;
	}

	.select-items__item {
		border: 1px solid #000;
		width: 100px;
		height: 40px;
		display: flex;
		justify-content: center;
		align-items: center;
	}
</style>
