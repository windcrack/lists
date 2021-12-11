<template lang="pug">
	div#app
		section.main
			.main__body(v-for="(item, i) in newObj" :key="i")
				ListsLeft(
					:lists="item" 
					:changerHandler="changerHandler" 
					:visible="visible"
				)
				ListsRight(:lists="item")
</template>

<script>
import ListsLeft from "./components/ListsLeft";
import ListsRight from "./components/ListsRight";
export default {
	name: "App",
	components: {
		ListsLeft, ListsRight
	},
	data(){
		return{
			newObj: {
				lists: [
					{count: 10, color: '#ff0000', chek: false},
					{count: 16, color: '#ffff00', chek: false},
					{count: 40, color: '#008000', chek: false},
					{count: 0, color: '#0000ff', chek: true},
				],
				lists2: [
					{count: 10, color: '#ff0000', chek: false},
					{count: 16, color: '#ffff00', chek: false},
					{count: 40, color: '#008000', chek: false},
					{count: 0, color: '#0000ff', chek: true},
				],
				lists3: [
					{count: 10, color: '#ff0000', chek: false},
					{count: 16, color: '#ffff00', chek: false},
					{count: 40, color: '#008000', chek: false},
					{count: 0, color: '#0000ff', chek: true},
					{count: 40, color: '#008000', chek: false},
				],
			},
			visible: false,
		}
	},

	methods: {
		changerHandler(){
			this.visible = !this.visible;
			for(let key in this.newObj){
				this.newObj[key].forEach( elem =>{
					elem.chek = !elem.chek
				})
			}
        }
	},
};
</script>

<style lang="sass">
	#app
		font-family: Avenir, Helvetica, Arial, sans-serif
		-webkit-font-smoothing: antialiased
		-moz-osx-font-smoothing: grayscale
		text-align: center
		color: #2c3e50
		margin-top: 60px
		display: flex
	*
		margin: 0
		padding: 0
	
	.main
		display: flex
		flex-wrap: wrap	
		border: solid 1px #000
		padding: 10px 20px
		margin-left: 12px
		&__body
			display: flex
</style>
