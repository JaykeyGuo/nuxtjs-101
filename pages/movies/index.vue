<template>
  <section class="movies">
    <Movie 
      v-for="movie in movies"
      :key="movie.id"
      :thumbnail="movie.thumbnail"
      :id="movie.id"
      :title="movie.title"
      :previewText="movie.previewText" />
  </section>
</template>

<script>
import Movie from '@/components/Movie'
import { resolve } from 'q';

export default {
  components: {
    Movie
  },
  asyncData() {
    return new Promise((resolve, reject) => {
      setTimeout(() => {
        resolve({
          movies: [
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
          ]
        })
      }, 1500)
    })
  }
}
</script>


<style scoped>
.movies {
  display: flex;
  flex-flow: row wrap;
  justify-content: center;
}

.movie {
  box-sizing: border-box;
  width: 260px;
  padding: 8px;
  border: 1px solid #ccc;
  box-shadow: 0 2px 2px #bbb;
  margin: 10px;
}

.thumbnail {
  background-position: center;
  background-size: cover;
  width: 100%;
  height: 200px;
}
</style>

