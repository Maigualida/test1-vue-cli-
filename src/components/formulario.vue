<template>
<div class="row">
    <div class="input-field col s6">
      <input v-model="newPers.nom" type="text" class="validate">
      <label class="active" for="first_name2">Add </label> 
			<a @click="myAdd()" class="btn-floating btn-large waves-effect waves-light red"><i class="material-icons">add</i></a>
    </div>
  </div>
            
</template>

<script>
export default{
	name: 'formulario',
  data () {
    return {
       newPers: {
       nom: "",
       photo: "https://www.thesun.co.uk/wp-content/uploads/2016/12/nintchdbpict000246685767.jpg?strip=all&w=960&quality=100",
      },
    }
  },
 
	
	methods:{
  myAdd(){
    this.$emit('addP',this.newPers);
    this.newPers= {}
  },
	}
}

</script>

<style scoped>




</style>