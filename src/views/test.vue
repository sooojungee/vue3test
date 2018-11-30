<template>
  <div class="ui-component">
    <div class="test-button-container">
      <div class="alert-button">
        <input class="alert alert-input" v-model="text"/>
        <!--<div class= "alert alert-message alert-success"> alert-success-button </div>-->
        <!--<div class= "alert alert-message alert-info"> alert-info-button </div>-->
        <!--<div class= "alert alert-message alert-warning"> alert-warning-button </div>-->
        <div class= "alert alert-message alert-error" @click="clickError"> alert-error-button </div>
      </div>
    </div>
    <div class="test-component-container">
      <v-alert class="alert-component" :value="3.456" :origin="'bottom left 100'" type="success"> This is a success alert. </v-alert>
      <v-alert class="alert-component" :value="true" type="info"> This is a info alert. </v-alert>
      <v-alert class="alert-component" :value="true" type="warning"> This is a warning alert. </v-alert>
      <v-alert class="alert-component" :value="errorValue" type="error" mode="out-in"
               :dismissible="true" icon="bookmark" transition="scale-transition" origin="bottom"> {{errorText}} </v-alert>
    </div>
  </div>
</template>

<script>
export default {
  name: 'test',
  data() {
    return {
      errorValue: false,
      errorText: 'This is a error alert.',
      text: ''
    };
  },
  methods: {
    clickError() {
      if (this.text.length > 0) this.errorText = this.text;
      else this.errorText = 'This is a error alert.';
      this.errorValue = !this.errorValue;
    }
  }
};
</script>

<style scoped lang="sass">
*
  margin: 0
  padding: 0
  font-size: 16px
.test-button-container
  width: 100%
  padding: 16px
  border-bottom: 2px solid #ccc
.alert-button
  display: flex
  .alert-input
  .alert
    padding: 8px
    margin-right: 4px
    border-radius: 8px
    border: 1px solid #ccc
  .alert-message
    cursor: pointer
  .alert-info
    border-color: #3c72ff
  .alert-warning
    border-color: #ffc965
  .alert-error
    border-color: #ed4f3b
  .alert-success
    border-color: #008000
.test-component-container
  padding: 16px
  width: 100%
  height: 1000px
  background: aliceblue
.alert-component
  width: 300px
  padding: 20px 24px
  margin: 16px
h1

</style>
