<template>
    <div class="bg-warning rounded">
      <div class="d-grid gap-3 rounded shadow-lg">
        <div class="px-3 px-lg-5 px-lg-3 py-3 py-lg-5 py-lg-3">
        	<div v-for="section in sections" class="alert" role="alert" @mouseenter="changeBgColor(section)" @mouseleave="changeBgColor(section)" :class="[section.is_active ? section.class_name : 'alert-dark']">
        		<h1 class="display-1 fw-bold lh-1">
        			{{ section.title }}
        		</h1>
        	</div>
        </div>
      </div>
    </div>
</template>

<script>
export default {
	data(){
		return{
			sections:{
				full_name:{
					is_active: false,
					title:"Course Catalogue",
					class_name: "alert-primary"
				},
				first_title:{
					is_active: false,
					title:"Teacher Assistant",
					class_name: "alert-warning"
				},
				second_title:{
					is_active: false,
					title:"Omid Reza Heidari",
					class_name: "alert-danger"
				}
			}
		}
	},
  	methods:{
  		changeBgColor(section){
	  		section.is_active=!section.is_active
  		}
  	}
}
</script>