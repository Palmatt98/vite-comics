<template>
	<div class="card">
		<img :src="cardImage" :alt="cardTitle" class="product-image">
		<p>{{ cardTitle }}</p>
	</div>
</template>

<script>
export default {
	props: {
		cardImage: String,
		cardTitle: String,
	},
};
</script>

<style lang="scss" scoped>
.product-image {
	width: 100%;
	height: 180px;
	object-fit: cover;
}
.card {
	width: calc((100% / 6) - 20px);
	margin: 0 10px;
	margin-bottom: 40px;
	p {
		margin-top: 12px;
		text-transform: uppercase;
	}
}
</style>
