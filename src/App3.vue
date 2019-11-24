<template>
  <div id="app">
    <h1>Template Interpolation</h1>
    <div>
      <p>Paragraph</p>
      <p>first Name: {{firstName}}</p>
      <p>last Name: {{lastName}}</p>
      <p>full Name: {{fullName}}</p>
    </div>
  </div>
</template>

<script>
export default {
  name: "app",
  data() {
    return {
      firstName: "Juan",
      lastName: "Perez",
      packtLink: "packtpub.com",
      complexObject: {
        id: 1,
        enabled: false,
        relatedItems: [2, 51, 31, 27, 96]
      }
    };
  },
  computed: {
    fullName() {
      return this.firstName + " " + this.lastName;
    }
  }
};
</script>