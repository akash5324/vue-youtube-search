<template>
	
	<div>
		<ul class="list-item">

			<videolistitem v-for="video in myvideolist" :video="video" :key="video.etag" @videoClicked="videoClicked">
					
			</videolistitem>
		</ul>
		
	</div>

</template>
<script>
	
	import videolistitem from './videolistitem';
	export default {

		name:'videolist',
		props:['myvideolist'],
		components:{

			videolistitem:videolistitem

		},
		methods:{

			videoClicked:function(video){

				this.$emit('onvideoclicked',video);
			}

		}
	};

</script>

<style>

	
</style>