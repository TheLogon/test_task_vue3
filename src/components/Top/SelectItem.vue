<template>
	<div class="select-item">
		<div class="select-item__flex">
			<div class="select-item__item">
				{{ itemRight.radioItem }}
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name: "SelectItem",
		props: ["itemRight"],
	}
</script>

<style>
	.select-item {
		display: flex;
		flex-direction: column;
		justify-content: space-between;
		align-items: center;
		border: 1px solid #000;
		padding: 10px;
		max-width: 342px;
		width: 100%;
	}

	.select-item__flex {
		display: flex;
		flex-wrap: wrap;
		margin-bottom: 10px;
		gap: 10px;
	}

	.select-item__item {
		border: 1px solid #000;
		width: 100px;
		height: 40px;
		display: flex;
		justify-content: center;
		align-items: center;
	}
</style>
