<template lang="pug">
	div#app
		section.main
			ListsLeft(
				:lists="lists" 
				:changerHandler="changerHandler" 
				:visible="visible"
			)
			ListsRight(:lists="lists")
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
			lists: [
				{count: 10, color: '#ff0000', chek: false},
				{count: 16, color: '#ffff00', chek: false},
				{count: 40, color: '#008000', chek: false},
				{count: 0, color: '#0000ff', chek: true},
			],
			visible: false,
			aciveId: null,
		}
	},

	methods: {
		changerHandler(){
			this.visible = !this.visible;
            this.lists.forEach((element) => {
				element.chek = !element.chek
			});
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

</style>
