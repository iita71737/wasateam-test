<template>
  <div>
    <ul class="list-group" v-for="item in listData" :key="item.id">
      <li class="list-group-item">{{ item.name }}</li>
      <li class="list-group-item">{{ item.city }}</li>
    </ul>
  </div>
</template>

<script>
export default {
  name: "List",
  props: {
    listData: {
      type: Object,
      required: true,
    },
  },
};
</script>
