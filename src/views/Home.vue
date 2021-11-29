<template>
  <div>
    <div class="card">
      <div class="card-header">Featured</div>
      <div class="card-body">
        <h5 class="card-title">
          <h1>Title: {{ this.typeProps }}</h1>
        </h5>
        <p class="card-text">
          <InputType :inputType="typeProps" />
        </p>
        <p>Description: Now the input type is {{ this.typeProps }}</p>
        <button
          type="button"
          class="btn btn-primary mr-2"
          @click="changeText()"
        >
          Change to Text
        </button>
        <button
          type="button"
          class="btn btn-success mr-2"
          @click="changeRadio()"
        >
          Change to Radio
        </button>

        <button
          type="button"
          class="btn btn-warning mr-2"
          @click="changeSelect()"
        >
          Change to Select
        </button>
      </div>
    </div>
    <div class="m-2" v-if="listData">
      <List :list-data="listData" />
    </div>
  </div>
</template>

<script>
// @ is an alias to /src
import InputType from "@/components/InputType.vue";
import List from "@/components/List.vue";
import axios from "axios";

export default {
  name: "Home",
  components: {
    InputType,
    List,
  },
  data() {
    return {
      typeProps: "text",
      listData: "",
    };
  },
  created() {
    this.fetchAPI();
  },
  methods: {
    changeText() {
      this.typeProps = "text";
      document.documentElement.setAttribute("data-theme", "light");
    },
    changeRadio() {
      this.typeProps = "radio";
      document.documentElement.setAttribute("data-theme", "green");
    },
    changeSelect() {
      this.typeProps = "select";
      document.documentElement.setAttribute("data-theme", "yellow");
    },
    async fetchAPI() {
      try {
        await axios
          .get("https://mocki.io/v1/d4867d8b-b5d5-4a48-a4ab-79131b5809b8")
          .then((response) => {
            console.log(response.data);
            this.listData = { ...response.data };
          });
      } catch (error) {
        console.log("error", error);
      }
    },
  },
};
</script>

<style lang="scss" scoped>
@import "../assets/scss/application.scss";
</style>
