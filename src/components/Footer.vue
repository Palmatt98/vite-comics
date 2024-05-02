<template>
	<footer>
		<div class="footer-top">
			<div class="container">
				<div class="links">
					<ul>
						<h4>DC COMICS</h4>
						<li v-for="link in dcComicsLinks">{{ link }}</li>
					</ul>
					<ul>
						<h4>SHOP</h4>
						<li v-for="link in shopLinks">{{ link }}</li>
					</ul>
					<ul>
						<h4>DC</h4>
						<li v-for="link in dcLinks">{{ link }}</li>
					</ul>
					<ul>
						<h4>SITES</h4>
						<li v-for="link in sitesLinks">{{ link }}</li>
					</ul>
				</div>
			</div>
		</div>
		<div class="footer-bottom">
			<div class="container">
				<div class="button">SIGN-UP NOW!</div>
				<div class="socials">
					<h3>FOLLOW US</h3>
					<div class="social">
						<i class="fa-brands fa-facebook-f"></i>
					</div>
					<div class="social">
						<i class="fa-brands fa-twitter"></i>
					</div>
					<div class="social">
						<i class="fa-brands fa-youtube"></i>
					</div>
					<div class="social">
						<i class="fa-brands fa-pinterest-p"></i>
					</div>
					<div class="social">
						<i class="fa-solid fa-location-dot"></i>
					</div>
				</div>
			</div>
		</div>
	</footer>
</template>

<script>
export default {
	data() {
		return {
			dcComicsLinks: ["Characters", "Comics", "Movies", "TV", "Games", "Videos", "News"],
			shopLinks: ["Shop DC", "Shop DC Collectibles"],
			dcLinks: [
				"Therm Of Use",
				"Pivacy Policy (New)",
				"Ad Choices",
				"Advertising",
				"Jobs",
				"Subscrictions",
				"Talent Workshops",
				"CPSC Certificates",
				"Ratings",
				"Shop Help",
				"Contact Us",
			],
			sitesLinks: ["DC", "MAD Magazine", "DC Kids", "DC Universe", "DC Power Visa"],
		};
	},
};
</script>

<style lang="scss" scoped>
@use "../style/partials/mixin" as *;
@use "../style/partials/variables" as *;
.footer-top {
	background-image: url("../assets/img/footer-bg.jpg");
	.container {
		padding: 30px 0;
		background-image: url("../assets/img/dc-logo-bg.png");
		background-repeat: no-repeat;
		background-position: right;
		.links {
			@include flex(column, start, start);
			max-height: 400px;
			flex-wrap: wrap;
			width: fit-content;
			ul {
				margin-right: 30px;
				margin-bottom: 30px;
				li {
					color: #959595;
					padding-bottom: 4px;
					cursor: pointer;
					&:hover {
						text-decoration: underline;
					}
				}
			}
			h4 {
				color: white;
				margin-bottom: 10px;
			}
		}
	}
}
.footer-bottom {
	height: 80px;
	background-color: #303030;
	.button {
		cursor: pointer;
		padding: 8px 14px;
		color: white;
		border: 2px solid $primary-color;
	}
	.container {
		@include flex(row, space-between, center);
		height: 100%;
	}
	.socials {
		@include flex(row, space-around, center);
		h3 {
			color: $primary-color;
			cursor: pointer;
		}
		.social {
			color: #303030;
			background-color: #797979;
			border-radius: 50%;
			height: 30px;
			width: 30px;
			@include flex(row, center, center);
			margin-left: 10px;
			cursor: pointer;
		}
	}
}
</style>
