<template>
	<div class="grid">
		<SelectItems :itemsLeft="selectedItems" />
		<SelectItem :itemRight="selectedItem" />
		<ItemsLeft :items="itemsLeft" @updateLeft="onUpdateItems" />
		<ItemsRight :items="itemsRight" @updateRight="onUpdateItem" />
	</div>
</template>

<script>
	import SelectItem from "@/components/Top/SelectItem.vue"
	import SelectItems from "@/components/Top/SelectItems.vue"
	import ItemsLeft from "@/components/Bottom/ItemsLeft.vue"
	import ItemsRight from "@/components/Bottom/ItemsRight.vue"

	export default {
		name: "App",
		components: {
			SelectItems,
			SelectItem,
			ItemsLeft,
			ItemsRight,
		},
		data() {
			return {
				itemsLeft: [
					{
						id: 1,
						name: "Shoes 1",
					},
					{
						id: 2,
						name: "Shoes 2",
					},
					{
						id: 3,
						name: "Shoes 3",
					},
					{
						id: 4,
						name: "Shoes 4",
					},
					{
						id: 5,
						name: "T-shirt 1",
					},
					{
						id: 6,
						name: "T-shirt 2",
					},
					{
						id: 7,
						name: "T-shirt 3",
					},
					{
						id: 8,
						name: "T-shirt 4",
					},
				],

				itemsRight: [
					{
						id: 11,
						name: "Jacket 1",
					},
					{
						id: 12,
						name: "Jacket 2",
					},
					{
						id: 13,
						name: "Jacket 3",
					},
					{
						id: 14,
						name: "Jacket 4",
					},
					{
						id: 15,
						name: "Hoodie 1",
					},
					{
						id: 16,
						name: "Hoodie 2",
					},
					{
						id: 17,
						name: "Hoodie 3",
					},
					{
						id: 18,
						name: "Hoodie 4",
					},
				],

				selectedItems: [],
				selectedItem: "",
			}
		},
		methods: {
			onUpdateItems(data) {
				this.selectedItems = data
			},
			onUpdateItem(item) {
				this.selectedItem = item
			},
		},
	}
</script>

<style>
	* {
		box-sizing: border-box;
	}

	body {
		padding: 0;
		margin: 0;
		background-color: #fff;
		color: #000;
	}

	h2 {
		font-size: 25px;
		text-transform: uppercase;
		text-align: center;
	}

	.grid {
		display: grid;
		grid-template-columns: 1fr 1fr;
		grid-template-rows: 1fr 1fr;
		gap: 40px 32px;
		justify-items: center;
		max-width: 1400px;
		margin: 0 auto;
	}

	#app {
		font-family: Avenir, Helvetica, Arial, sans-serif;
		-webkit-font-smoothing: antialiased;
		-moz-osx-font-smoothing: grayscale;
	}
</style>
