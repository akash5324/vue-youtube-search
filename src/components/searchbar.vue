<template>
	
	<div>
		<input placeholder="search your query from youtube......" @input="onInput" />
	</div>

</template>
<script>
	
	export default {

		name:'searchbar',
		methods:{

			onInput:function(event) {

				this.$emit('valueChange',event.target.value);

			}
		}
	};

</script>

<style scoped>
	
	input{

		width:80%;
		height: 70px;
		background-color: #dcdcdc;
		padding:13px;
		-webkit-box-sizing:border-box;
		-moz-box-sizing:border-box;
		box-sizing:border-box;
		border-radius:6px;
		-webkit-box-shadow:
		0 2px 4px 0 rgba(72, 72, 72, 0.83),
		0 10px 15px 0 rgba(126, 126, 126, 0.12),
		0 -2px 6px 1px rgba(199, 199, 199, 0.55) inset,
		0 2px 4px 2px rgba(255, 255, 255, 0.83) inset;
		-moz-box-shadow:
		0 2px 4px 0 rgba(72, 72, 72, 0.83),
		0 10px 15px 0 rgba(126, 126, 126, 0.12),
		0 -2px 6px 1px rgba(199, 199, 199, 0.55) inset,
		0 2px 4px 2px rgba(255, 255, 255, 0.83) inset;
		box-shadow:
		0 2px 4px 0 rgba(72, 72, 72, 0.83),
		0 10px 15px 0 rgba(126, 126, 126, 0.12),
		0 -2px 6px 1px rgba(199, 199, 199, 0.55) inset,
		0 2px 4px 2px rgba(255, 255, 255, 0.83) inset; 
	},

	div{

		text-align: center;
		margin: 5%;
	}

</style>