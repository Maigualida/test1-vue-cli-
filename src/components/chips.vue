<template>

  <div class="chip">
    <img :src="pers.photo" alt="Contact Person">
   {{pers.nom}}
  </div>

</template>

<script>
export default{
	name: "chips",
	props: ["pers"]

}

</script>

<style scoped>

</style>