<template>
	<div class="items-right">
		<h2 class="items-right__title">Выбери вещь</h2>
		<div class="items-right__form">
			<div v-for="item in items" :key="item.id" class="items-right__item">
				<input type="radio" @change="addRight()" class="items-right__radio" name="items" :value="item.name" v-model="itemRadio" :id="item.id" />
				<label :for="item.id">{{ item.name }}</label>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name: "ItemsRight",
		props: ["items"],
		data() {
			return {
				itemRadio: "",
			}
		},
		methods: {
			addRight() {
				this.$emit("updateRight", {
					radioItem: this.itemRadio,
				})
			},
		},
	}
</script>

<style>
	.items-right__form {
		display: flex;
		align-items: center;
		flex-wrap: wrap;
		gap: 20px;
	}

	.items-right__item {
		width: 120px;
		height: 40px;
		display: flex;
		justify-content: center;
		align-items: center;
		border: 1px solid #3d3d3d;
		cursor: pointer;
	}

	.items-right__item input {
		display: none;
	}

	.items-right__item input:checked + label {
		color: #00ff00;
	}
	.items-right__item label {
		cursor: pointer;
	}
</style>
