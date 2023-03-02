<template>
    <div>
	<div class="grid-container">
		<div v-for="(products, i) in productSet" :key = "i" class="row">
			<div v-for="product in products" :key="product.name" class="product-box">
				<img :src="product.img" alt="">
				<div class="info">
					<div class="info-left"><span>{{ product.name }}</span><span>Size: {{ product.size }}</span></div>
					<div class="info-right">Price: {{ product.price }}</div>
				</div>
			</div>
		</div>
	</div>
    </div>
</template>

<script>
import NavBar from './NavBar.vue';


export default {

	name: 'App',
	data() {
		return {
			productSet: [
				[{
					name: 'Shirt 1',
					img: "https://picsum.photos/500/300",
					size: 'XL',
					price: '100'
				},
				{
					name: 'Blue Flower Shirt 2',
					img: "https://picsum.photos/500/300",
					size: 'L',
					price: '200'
				},
				{
					name: 'Shirt 3',
					img: "https://picsum.photos/500/300",
					size: 'M',
					price: '800'
				},],
				[{
					name: 'Pant 1',
					img: "https://picsum.photos/500/300",
					size: 'S',
					price: '150'
				},
				{
					name: 'Skirt 1',
					img: "https://picsum.photos/500/300",
					size: 'XS',
					price: '69'
				},
				{
					name: 'Unnecessarily large garment name',
					img: "https://picsum.photos/500/300",
					size: 'L',
					price: '400'
				},],
			]
		};
	},
	components: {
    NavBar
}
};
</script>

<style>
#app {
	font-family: Avenir, Helvetica, Arial, sans-serif;
	-webkit-font-smoothing: antialiased;
	-moz-osx-font-smoothing: grayscale;
	color: #2c3e50;
	margin-top: 60px;
}

.grid-container {
	border: none;
	margin: 0 auto;
}

.row {
	display: flex;
	gap: 100px;
	padding: 10px;
}

.product-box {
	background-color: lightgrey;
	display: grid;
	grid-row: repeat(2, 1fr);
	border-radius: 20px;
	align-content: center;
	padding: 20px 0;
	font-size: 30px;
}

img {
	max-width: 100%;
	border-radius: 10px;
	height: auto;
	width: auto\9;
	/* ie8 */
}

.info {
	font-size: 20px;
	display: flex;
	flex-direction: column;
	overflow-wrap:break-word;
	flex-wrap: wrap;
}

.info-left {
	/* align-self:flex-start; */
	text-overflow: ellipsis;
	overflow: hidden;
	align-self: flex-start;
	display: grid;
	grid-template-rows: auto auto;
	padding-inline: 10px;
}

.info-right {
	align-self: flex-end;
	padding-inline: 10px;
}
</style>
