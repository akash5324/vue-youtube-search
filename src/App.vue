<template>
	
	<div class="container">
		<searchbar @valueChange="onSearch"></searchbar>
			
			<div class="row">
				
					<div class="col-md-8" v-if="url">
					
					<div class="embed-responsive embed-responsive-16by9" >
					<iframe class="embed-responsive-item" :src="url" allowfullscreen>
					</iframe>
					</div>

					<div class="title">
						<h3>{{title}}</h3>
					</div>
					
					</div>
				
				<div class="col-md-4">
					
					<videolist v-bind:myvideolist="videos" @onvideoclicked="videoclicked"></videolist>
				</div>


					
				


			</div>
		
	</div>

</template>
<script>
	import searchbar from './components/searchbar';
	import videolist from './components/videolist';
	import axios from 'axios';
	const API_KEY = 'your api key';
	export default {

		name:'App',
		components:{

			searchbar:searchbar,
			videolist:videolist
		},


		data:function(){

			return { 
			videos:[],
			url:'',
			title:'',
			description:'' };

		},
		methods:{

			onSearch:function(searchItem){

				axios.get('https://www.googleapis.com/youtube/v3/search',{

					params:{

						key:API_KEY,
						type:'video',
						part:'snippet',
						q:searchItem,
						maxResults: '30'

					}
				})
				.then(response=>{

					this.videos=response.data.items;
					//console.log(response);

				});
			},

			videoclicked:function(video){

			const id=video.id.videoId;
			const title=video.snippet.title;
			const description=video.snippet.description;

			this.url='https://www.youtube.com/embed/'+id;
			this.title=title;
			this.description=description;

			console.log(this.url);

			}
		}

	};

</script>

<style type="text/css">
	
	iframe {
-moz-border-radius: 12px;
-webkit-border-radius: 12px;
border-radius: 20px;
box-shadow: 4px 4px 14px #fc8080;
}
</style>