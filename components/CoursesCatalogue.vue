<template>
	<div class="d-grid gap-2 container">
		<div class="d-grid gap-1" v-for="course in courses">
	      	<div class="alert-primary rounded p-2 p-lg-4 p-lg-2 row">
	        	<div class="d-grid gap-2 col-5">
	        		<div class="d-flex justify-content-left">
	        			<img src="https://img.icons8.com/bubbles/1000/book.png" class="ico icon" />
	        			<div class="ms-2 horizental-centric-1">
	        				{{ course.name }}
	        			</div>
	        		</div>
	        		<div>
	        			<img class="ico icon" v-for="topic in course.topics" :name='topic.name' :src="topic.source" />
	        		</div>
	        	</div>
	        	<div class="d-grid gap-2 col-4">
	        		<div class="d-flex justify-content-left">
	        			<img src="https://img.icons8.com/bubbles/1000/calendar--v2.png" class="ico icon" />
	        			<div class="ms-2 horizental-centric-1">
	        				{{ course.semester }} {{ course.year }}
	        			</div>
	        		</div>
	        		<div class="d-flex justify-content-left">
	        			<img src="https://img.icons8.com/bubbles/1000/education.png" class="ico icon" />
	        			<div class="ms-2 horizental-centric-1">
	        				{{ course.university }}
	        			</div>
	        		</div>
	        	</div>
	        	<div class="col-3">
	        		<div class="d-flex justify-content-left">
		        		<a
		        			v-show="course.link"
		        			:href="course.link"
		        			@mouseenter="update_link_text_visablity(course)"
		        			@mouseleave="update_link_text_visablity(course)"
		        		>
							<img src="https://img.icons8.com/bubbles/1000/link.png" class="ico link-icon"/>
						</a>
						<span class="horizental-centric-2" v-show="course.link_text_visablity">
							{{ course.link_text }}
						</span>
					</div>
	        	</div>
	    	</div>
	    </div>
	    <div></div>
	</div>
</template>

<style>
.icon{
	width: 50px;
	height: 50px;
}
.link-icon{
	width: 100px;
	height: 100px;	
}
</style>

<style>
.horizental-centric-1{
	padding-top: 2%;
}
.horizental-centric-2{
	padding-top: 13%;
}
</style>

<script>
export default {
	data(){
		return{
			courses:[
				{
					year:'2024',
					name:'Databases',
					semester:'Winter',
					university:'Concordia University',
					link:'https://teacher-assistant.github.io/winter2024-Databases/',
					link_text_visablity:false,
					link_text:'Website of the course',
					topics:[
						{
							name:'postgresql',
							source:'https://img.icons8.com/bubbles/1000/database.png'
						},
						{
							name:'github',
							source:'https://img.icons8.com/bubbles/1000/github.png'
						},
						{
							name:'git',
							source:'https://img.icons8.com/bubbles/1000/code-fork.png'
						}
					]
				},
				{
					year:'2022',
					name:'Machine Learning',
					semester:'Fall',
					university:'Sharif University of Technology',
					link:'https://github.com/asharifiz/Introduction_to_Machine_Learning',
					link_text_visablity:false,
					link_text:'GitHub of the Course',
					topics:[
						{
							name:'math',
							source:'https://img.icons8.com/bubbles/1000/repository.png'
						},
						{
							name:'python',
							source:'https://img.icons8.com/clouds/1000/python.png'
						},
						{
							name:'terminal',
							source:'https://img.icons8.com/bubbles/1000/console.png'
						},
						{
							name:'github',
							source:'https://img.icons8.com/bubbles/1000/github.png'
						},
						{
							name:'git',
							source:'https://img.icons8.com/bubbles/1000/code-fork.png'
						}
					]
				},
				{
					year:'2022',
					name:'Principles of Database Design',
					semester:'Winter',
					university:'University of Zanjan',
					link:'https://teacher-assistant.github.io/winter2022-PrinciplesOfDatabaseDesign',
					link_text_visablity:false,
					link_text:'Website of the Course',
					topics:[
						{
							name:'python',
							source:'https://img.icons8.com/clouds/1000/python.png'
						},

						{
							name:'postgresql',
							source:'https://img.icons8.com/bubbles/1000/database.png'
						},
						{
							name:'github',
							source:'https://img.icons8.com/bubbles/1000/github.png'
						},
						{
							name:'git',
							source:'https://img.icons8.com/bubbles/1000/code-fork.png'
						}
					]
				},
				{
					year:'2022',
					name:'Advance Programming',
					semester:'Winter',
					university:'Islamic Azad University, Zanjan Branch',
					link:'https://teacher-assistant.github.io/winter2022-AdvanceProgramming',
					link_text:'Website of the Course',
					link_text_visablity:false,
					topics:[
						{
							name:'python',
							source:'https://img.icons8.com/clouds/1000/python.png'
						},
						{
							name:'github',
							source:'https://img.icons8.com/bubbles/1000/github.png'
						},
						{
							name:'git',
							source:'https://img.icons8.com/bubbles/1000/code-fork.png'
						}
					]
				},
				{
					year:'2021',
					name:'Digital Logic Design',
					semester:'Fall',
					university:'University of Zanjan',
					link:'https://teacher-assistant.github.io/fall2021-DigitalLogicDesign',
					link_text:'Website of the Course',
					link_text_visablity:false,
					topics:[
						{
							name:'math',
							source:'https://img.icons8.com/bubbles/1000/repository.png'
						},
						{
							name:'microchip',
							source:'https://img.icons8.com/bubbles/1000/motherboard.png'
						}
					]
				}
			]
		}
	},
	methods:{
		update_link_text_visablity(course){
			course.link_text_visablity =! course.link_text_visablity;
		}
	}
}
</script>