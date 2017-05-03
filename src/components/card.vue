<template>
<div class="row algo">
        <div class="col s9" >
          <div class="card" :class="{amber: bar}">
            <div class="card-image" >
            <div class="col s3">
              <img :src="pers.photo" height="130">
              
              <span class="card-title"></span>
              </div>
            </div>
            <div class="card-content">

              <p> {{pers.nom}}</p>
              <p>{{pers.biographie}}</p>

              <div v-if="pers.sexe == true"><p>C'est un homme</p></div>
              
               <div v-else><p>C'est un femme</p></div>

            </div>
            <div class="card-action">
              <button type="button" @click="myDelete(pers)" class="btn-floating btn-large waves-effect waves-light red"><i class="material-icons">delete</i></button>
            </div>
          </div>
        </div>
      </div>
            
</template>

<script>
export default{
	name: "card",
	props: ['pers'],
  	computed: {
		bar: function () {
      let regex = new RegExp(".+Baratheon.+", "i");	
			return regex.test(this.pers.biographie);
		},
},
methods:{
  myDelete(pers){
    console.table(pers);
    this.$emit('deleteP');
  }
}

}

</script>

<style scoped>

.bars{
  background-color: red;
}

</style>