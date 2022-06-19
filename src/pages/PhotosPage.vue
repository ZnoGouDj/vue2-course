<template>
  <v-container>
    <v-row>
      <Photo v-for="photo in photos" :photo="photo" :key="photo.id" />
    </v-row>
  </v-container>
</template>

<script>
import Photo from '@/components/photo/Photo';
export default {
  components: {
    Photo,
  },
  data: () => ({
    photos: [
      { id: 1, title: 'Photo 1' },
      { id: 2, title: 'Photo 2' },
      { id: 3, title: 'Photo 3' },
      { id: 4, title: 'Photo 4' },
      { id: 5, title: 'Photo 5' },
      { id: 6, title: 'Photo 6' },
    ],
  }),
  mounted() {
    this.fetchTodo();
  },
  methods: {
    fetchTodo() {
      this.axios
        .get('https://jsonplaceholder.typicode.com/photos?_limit=10')
        .then(response => (this.photos = response.data));
    },
  },
};
</script>

<style lang="scss" scoped></style>
