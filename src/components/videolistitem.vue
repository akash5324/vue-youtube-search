<template>
	

		<li class="list-group-item media" @click="clickedItem">
		
		<img  :src="video.snippet.thumbnails.high.url">
		<div class="media-body">
			
			<h5>{{video.snippet.title}}</h5>

		</div> 
		</li>
		

</template>
<script>
	
	export default {

		name:'videolistitem',
		props:['video'],
		methods:{

			clickedItem:function(){

				this.$emit('videoClicked',this.video);
			}

		}
	};

</script>

<style scoped>

li{

	display: flex;
	justify-content: center;
	-moz-border-radius: 12px;
-webkit-border-radius: 12px;
border-radius: 15px;
box-shadow: 4px 4px 14px lightblue;
}

img{

	margin-right:2%;
	height: 120px;
	width: 120px;
}

li:hover{

	cursor: pointer;
	background-color: #fc8080;
}
	
</style>