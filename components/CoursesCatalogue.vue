<template>
	<div class="d-grid gap-2 container">
		<div class="d-grid gap-1" v-for="course in courses">
	      	<div class="alert-primary rounded p-2 p-lg-4 p-lg-2 row">
	        	<div class="d-grid gap-2 col-5">
	        		<div class="d-flex justify-content-start">
	        			<box-icon name='book'></box-icon>
	        			<div class="ms-2">
	        				{{ course.name }}
	        			</div>
	        		</div>
	        		<div>
	        			<box-icon v-for="topic in course.topics" size="md" :type="topic.type" :name='topic.name'></box-icon>
	        		</div>
	        	</div>
	        	<div class="d-grid gap-2 col-5">
	        		<div class="d-flex justify-content-start">
	        			<box-icon name='calendar'></box-icon>
	        			<div class="ms-2">
	        				{{ course.semester }} {{ course.year }}
	        			</div>
	        		</div>
	        		<div class="d-flex justify-content-start">
	        			<box-icon type='solid' name='school'></box-icon>
	        			<div class="ms-2">
	        				{{ course.university }}
	        			</div>
	        		</div>
	        	</div>
	        	<div class="col-2">
	        		<a
	        			v-show="course.link"
	        			type="button"
	        			class="btn btn-dark"
	        			:href="course.link"
	        		>
	        		<div class="d-flex justify-content-start">
	        			<box-icon name='link' color='white' ></box-icon>
						<div class="ms-2">
							Course page
						</div>
	        		</div>
					</a>
	        	</div>
	    	</div>
	    </div>
	    <div></div>
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