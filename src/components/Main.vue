<template>
	<main>
		<div class="jumbotron">
			<img src="../assets/img/jumbotron.jpg" alt="" />
		</div>
		<div class="container">
			<div class="up-main">
				<div class="title">
					<h2>CURRENT SERIES</h2>
				</div>
				<div class="row">
					<ProductCard
						v-for="comicBook in comicBooks"
						:cardImage="comicBook.thumb"
						:cardTitle="comicBook.series"
					/>
				</div>
				<div class="button">LOAD MORE</div>
			</div>
		</div>
		<div class="icon">
			<div class="container">
				<ul>
					<li v-for="image in images">
						<img :src="getImageUrl(image.image)" alt="" class="icon-image" />
						<p>{{ image.title }}</p>
					</li>
				</ul>
			</div>
		</div>
	</main>
</template>

<script>
import ProductCard from "./ProductCard.vue";

export default {
	components: {
		ProductCard,
	},
	data() {
		return {
			images: [
				{
					image: "buy-comics-digital-comics.png",
					title: "DIGITAL COMISCS",
				},
				{
					image: "buy-comics-merchandise.png",
					title: "DC MERCHANDISE",
				},
				{
					image: "buy-comics-subscriptions.png",
					title: "SUBSCRIPTION",
				},
				{
					image: "buy-comics-shop-locator.png",
					title: "COMIC SHOP LOCATOR",
				},
				{
					image: "buy-dc-power-visa.svg",
					title: "DC POWER VISA",
				},
			],
			comicBooks: [
				{
					thumb: "https://www.coverbrowser.com/image/action-comics/1-1.jpg",
					price: "$19.99",
					series: "Action Comics",
					type: "comic book",
				},
				{
					thumb: "https://www.panini.it/media/catalog/product/cache/a5b5dd3adfe0d321084804c738f29601/M/1/M1BLLA015ISBN_0.jpg",
					price: "$3.99",
					series: "American Vampire 1976",
					type: "comic book",
				},
				{
					thumb: "https://media.wired.com/photos/593384dad80dd005b42b2817/master/w_2560%2Cc_limit/Aquaman-16.jpg",
					price: "$16.99",
					series: "Aquaman",
					type: "graphic novel",
				},
				{
					thumb: "https://d29xot63vimef3.cloudfront.net/image/batgirl/1-1.jpg",
					price: "$2.99",
					series: "Batgirl",
					type: "comic book",
				},
				{
					thumb: "https://static.posters.cz/image/750/locandine-film-in-plexiglass-batman-prowl-comic-cover-i69653.jpg",
					price: "$3.99",
					series: "Batman",
					type: "comic book",
				},
				{
					thumb: "https://static.wikia.nocookie.net/marvel_dc/images/5/50/Batman_Beyond_v.1_1.jpg",
					price: "$2.99",
					series: "Batman Beyond",
					type: "comic book",
				},
				{
					thumb: "https://static.wikia.nocookie.net/marvel_dc/images/0/0d/Batman_Superman_Vol_1_1.jpg",
					price: "$3.99",
					series: "Batman/Superman",
					type: "comic book",
				},
				{
					thumb: "https://static.wikia.nocookie.net/marvel_dc/images/c/cf/Batman_Superman_Annual_Vol_2_1.jpg",
					price: "$4.99",
					series: "Batman/Superman Annual",
					type: "comic book",
				},
				{
					thumb: "https://static.wikia.nocookie.net/marvel_dc/images/5/54/Batman_The_Joker_War_Zone_Vol_1_1.jpg",
					price: "$5.99",
					series: "Batman: The Joker War Zone",
					type: "comic book",
				},
				{
					thumb: "https://static.wikia.nocookie.net/marvel_dc/images/6/64/Batman_Three_Jokers_Collected.jpg",
					price: "$6.99",
					series: "Batman: Three Jokers",
					type: "comic book",
				},
				{
					thumb: "https://static.wikia.nocookie.net/marvel_dc/images/f/f8/Batman_White_Knight_Presents_Harley_Quinn_Vol_1_1.jpg",
					price: "$4.99",
					series: "Batman: White Knight Presents: Harley Quinn",
					type: "comic book",
				},
				{
					thumb: "https://static.wikia.nocookie.net/marvel_dc/images/c/c8/Catwoman_Vol_2_1.jpg",
					price: "$16.99",
					series: "Catwoman",
					type: "graphic novel",
				},
			],
		};
	},
	methods: {
		getImageUrl(image) {
			console.log("import.meta.url: ", import.meta.url);
			console.log("new URL(`../assets/img/${image}`, import.meta.url).href: ", new URL(`../assets/img/${image}`, import.meta.url).href);
			return new URL(`../assets/img/${image}`, import.meta.url).href;
		},
	},
};
</script>

<style lang="scss" scoped>
@use "../style/partials/variables" as *;
@use "../style/partials/mixin" as *;

main {
	background-color: #1c1c1c;

	.jumbotron {
		height: 320px;
		img {
			height: 100%;
			width: 100%;
			object-fit: cover;
			object-position: top;
		}
	}
	.up-main {
		color: white;
		padding-bottom: 30px;
		.title {
			background-color: $primary-color;
			width: fit-content;
			padding: 8px 20px;
			transform: translateY(-50%);
		}
	}
	.icon {
		// @include flex(row, space-around, stretch);
		color: #fff;
		background-color: $primary-color;
		padding: 50px 0;
		ul {
			display: flex;
			justify-content: space-between;
			li {
				display: flex;
				align-items: center;
				.icon-image {
					max-width: 50px;
					height: 50px;
				}
				p {
					margin-left: 10px;
				}
			}
		}
	}
	.row {
		display: flex;
		flex-wrap: wrap;
	}
	.button {
		font-weight: bold;
		background-color: $primary-color;
		width: fit-content;
		padding: 8px 50px;
		cursor: pointer;
		margin: 0 auto;
	}
}
</style>
