<template>
  <div class="about">
    <h1>This is an about page</h1>
  </div>
  <card-component></card-component>
</template>

<script>
import CardComponent from '@/components/CardComponent.vue';

export default {
  components: {
    CardComponent,
  },
};
</script>
