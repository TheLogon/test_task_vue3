<template>
	<div class="items-left">
		<h2 class="items-left__title">Твои вещи</h2>
		<div class="select-item__form">
			<div v-for="item in items" :key="item.id" class="select-item__item">
				<input type="checkbox" :disabled="itemCheck.length == 6" @change="addLeft()" class="select-item__checkbox" name="items" :value="item.name" v-model="itemCheck" :id="item.id" />
				<label :for="item.id">{{ item.name }}</label>
			</div>
		</div>
	</div>
</template>

<script>
	export default {
		name: "ItemsLeft",
		props: ["items"],
		data() {
			return {
				itemCheck: [],
			}
		},
		methods: {
			addLeft() {
				this.$emit("updateLeft", {
					checkItems: this.itemCheck,
				})
			},
		},
	}
</script>

<style>
	.select-item__form {
		display: flex;
		align-items: center;
		flex-wrap: wrap;
		gap: 20px;
	}

	.select-item__item {
		width: 120px;
		height: 40px;
		display: flex;
		justify-content: center;
		align-items: center;
		border: 1px solid #3d3d3d;
		cursor: pointer;
	}

	.select-item__item input {
		display: none;
	}

	.select-item__item input:checked + label {
		color: #00ff00;
	}
	.select-item__item label {
		cursor: pointer;
	}
</style>
