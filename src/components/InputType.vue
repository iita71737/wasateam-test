<template>
  <div>
    <div v-if="this.inputType === 'text'">
      <span>Message is: {{ message }}</span>
      <br />
      <input type="text" v-model="message" placeholder="edit me" />
    </div>

    <div v-if="this.inputType === 'radio'">
      <input type="radio" id="one" value="One" v-model="picked" />
      <label for="one">One</label>
      <br />
      <input type="radio" id="two" value="Two" v-model="picked" />
      <label for="two">Two</label>
      <br />
      <span>Picked: {{ picked }}</span>
    </div>

    <div v-if="this.inputType === 'select'">
      <select v-model="selected">
        <option selected>A</option>
        <option>B</option>
        <option>C</option>
      </select>
      <span>Selected: {{ selected }}</span>
    </div>
  </div>
</template>

<script>
export default {
  name: "InputType",
  props: {
    inputType: {
      type: String,
      required: true,
    },
  },
  data() {
    return {
      selected: "",
      picked: "",
      message: "",
    };
  },
  created() {
    this.fetchProps();
  },
  methods: {
    fetchProps() {},
  },
};
</script>
