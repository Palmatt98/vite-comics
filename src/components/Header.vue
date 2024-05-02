<template>
	<header>
		<div class="container">
			<div class="logo">
				<img src="../assets/img/dc-logo.png" alt="" />
			</div>
			<nav>
				<ul>
					<li v-for="item in menuItems" :class="item.isActive === true ? 'active' : ''">
						<a href="">{{ item.title }}</a>
					</li>
				</ul>
			</nav>
		</div>
	</header>
</template>

<script>
export default {
	data() {
		return {
			menuItems: [
				{
					title: "CHARACTERS",
					isActive: false,
				},
				{
					title: "COMICS",
					isActive: true,
				},
				{
					title: "MOVIES",
					isActive: false,
				},
				{
					title: "TV",
					isActive: false,
				},
				{
					title: "GAMES",
					isActive: false,
				},
				{
					title: "COLLECTIBLES",
					isActive: false,
				},
				{
					title: "VIDEOS",
					isActive: false,
				},
				{
					title: "FANS",
					isActive: false,
				},
				{
					title: "NEWS",
					isActive: false,
				},
				{
					title: "SHOP",
					isActive: false,
				},
			],
		};
	},
};
</script>

<style lang="scss" scoped>
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;
header {
	height: 80px;
}
.container {
	@include flex(row, space-between, center);
	height: 100%;
}
nav {
	height: 100%;
}
ul {
	height: 100%;
	@include flex(row, center, center);
	li {
		cursor: pointer;
		height: 100%;
		@include flex(row, center, center);
		transition: color 0.2s;
		&.active {
			color: $primary-color;
			box-shadow: inset 0px -3px 0px 0px $primary-color;
		}
		&:hover {
			color: $primary-color;
			box-shadow: inset 0px -3px 0px 0px $primary-color;
		}

		a {
			padding: 0 10px;
			font-weight: bold;
		}
	}
}
.logo {
	height: 70%;
	cursor: pointer;
	img {
		height: 100%;
	}
}
</style>
