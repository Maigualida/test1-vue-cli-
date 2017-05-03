<template>

	<div>

	<formulario @addP="addList($event)"></formulario>
		<div class="row">
		
    	 <div class="col s9">
					<preloader v-if="personage.length===0"></preloader>
					<cards :key="pers.id" :pers="pers" v-for='pers in personage' @deleteP="deleteL(pers)"></cards>
				</div>
				<div class="col s3">
        		<chips :class="{pulse:personage.length > 7, red: personage.length < 2 }" :key="pers.id" :pers="pers" v-for='pers in personage'></chips>
						<collection :key="pers.id" :pers="pers" v-for='pers in personage'></collection>
    		</div>

		</div>
	</div>
            
</template>

<script>
import card from './card.vue'
import preloader from './preloader.vue'
import chips from './chips.vue'
import collection from './collection.vue'
import formulario from './formulario.vue'
export default {
  components: {cards: card, preloader:preloader, chips:chips, collection: collection, formulario:formulario},
	name:'list',
  
  data () {
    return {
      personage: [],
			bar: false,
    }
  },

created: function () {
			// fonction (hook) qui se grefe dès la création de l'instance
			let url = "https://raw.githubusercontent.com/Symfomany/angu/master/datas/got.json";

			// Requete en AJAX de typ)e GET derriere une URL
			this.$http.get(url).then(function (reponse) {
				this.personage = JSON.parse(reponse.body); // body: corps de ma réponse
				console.log(this.personage);
			});
				},
methods: {
	deleteL(pers){
			let position = this.personage.indexOf(pers);
			this.personage.splice(position, 1);
	},
	addList(content){
		this.personage.push(content);
		console.log (content);
	}
}

}

</script>

<style scoped>

.container-p{
	
text-align: center;
padding-left: 20%;
}
</style>