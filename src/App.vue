<template>
  <div style="background:red">Prout {{ value }} <b>message:</b> {{ message }}</div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      value: "World",
      message: "-"
    };
  },
  async mounted() {
    const { text } = await (await fetch("/api/hello")).json();
    this.message = text;
  }
};
</script>
