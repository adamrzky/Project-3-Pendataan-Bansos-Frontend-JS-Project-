<template>
  <v-container 
    class="text-center"
    v-if="this.$route.params.savedForm"
  >
    <div class="header">
        <div class="header-content">

        </div>
    </div>
    <v-card
      class="mx-auto px-7 py-10 rounded-t-xl rounded-t-0"
      max-width="800"
      outlined
      elevation="3"
    >
      <h1 class="text-headline primary--text">
      Data Tersimpan
      </h1>

      <v-divider class="my-2"></v-divider>

      <v-btn
        rounded
        color="success"
        class="rounded-pill px-16 py-6"
        to="/"
      >
        Tambah Data Baru
      </v-btn>
    </v-card>
  </v-container>
</template>

<script>
  export default {
    beforeCreate(){
      if(!this.$route.params.savedForm){
        document.title = this.$route.meta.title
        this.$router.push("/")
      }else{
        document.title = "Berhasil disimpan"
      }
    },
  }
</script>