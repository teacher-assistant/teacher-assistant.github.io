<template>
	<div class="d-grid gap-2 container">
		<div class="d-grid gap-1" v-for="course in courses">
	      	<div class="alert-primary rounded p-2 p-lg-4 p-lg-2 row">
	        	<div class="d-grid gap-2 col-5">
	        		<span>
	        			<box-icon name='book'></box-icon>
	        			{{ course.name }}
	        		</span>
	        		<span>
	        			<box-icon v-for="topic in course.topics" size="md" :type="topic.type" :name='topic.name'></box-icon>
	        		</span>
	        	</div>
	        	<div class="d-grid gap-2 col-5">
	        		<span>
	        			<box-icon name='calendar'></box-icon>
	        			{{ course.semester }} - {{ course.year }}
	        		</span>
	        		<span>
	        			<box-icon name='world'></box-icon>
	        			{{ course.university }}
	        		</span>
	        	</div>
	        	<div class="col-2">
	        		<a
	        			v-show="course.link"
	        			type="button"
	        			class="btn btn-dark"
	        			:href="course.link"
	        		>
						Course Page
					</a>
	        	</div>
	    	</div>
	    </div>
	</div>
</template>

<script>
export default {
	data(){
		return{
			courses:[
				{
					year:'2022',
					name:'Principles Of Database Design',
					semester:'Winter',
					university:'University of Zanjan',
					link:'https://teacher-assistant.github.io/winter2022-PrinciplesOfDatabaseDesign',
					topics:[
						{
							name:'python',
							type:'logo'
						},
						{
							name:'postgresql',
							type:'logo'
						},
						{
							name:'github',
							type:'logo'
						}
					]
				},
				{
					year:'2022',
					name:'Advance Programming',
					semester:'Winter',
					university:'Islamic Azad University',
					link:'https://teacher-assistant.github.io/winter2022-AdvanceProgramming',
					topics:[
						{
							name:'python',
							type:'logo'
						},
						{
							name:'github',
							type:'logo'
						}
					]
				},
				{
					year:'2021',
					name:'Digital Logic Design',
					semester:'Fall',
					university:'University of Zanjan',
					link:'https://teacher-assistant.github.io/fall2021-DigitalLogicDesign',
					topics:[
						{
							name:'math',
							type:''
						},
						{
							name:'microchip',
							type:''
						}
					]
				}
			]
		}
	}
}
</script>