<template>
  <section class="single-movie">
    <hgroup>
      <h1>{{ movie.title }}</h1>
    </hgroup>
    <div>
      <img class="movie-image" :src="movie.thumbnail" :alt="movie.title">
    </div>
    <p>{{ movie.previewText }}</p>
  </section>
</template>

<script>
export default {
  asyncData(context) {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          movie: [
            {
              id: "1",
              title: "LEGO Movie",
              previewText: "The LEGO Big Movie",
              thumbnail: "https://target.scene7.com/is/image/Target/LEGOMOVIE2_010619_CatBrowse_328x32805_ALLLM2159477-181213_1544736191920?wid=328&hei=328&qlt=80&fmt=pjpeg"
            },
            {
              id: "2",
              title: "Disney Movie",
              previewText: "Frozen",
              thumbnail: "https://disneylandparisbonsplans.files.wordpress.com/2018/06/entete.jpg?w=604"
            }
          ].find(el => el.id === context.params.id)
        })
      }, 1500)
    })
  }
}
</script>


<style scoped>
.single-movie {
  display: flex;
  flex-flow: column;
  justify-content: center;
  align-content: center;
  text-align: center;
  border: 1px solid #ccc;
  margin: 10px;
  padding: 30px;
}

.movie-image {
  width: 100%;
}
</style>
