<template>
  <div :class="b()">
    <h1>Form example</h1>

    <h2>e-input</h2>
    <p>including e-label</p>
    <form>
      <e-label name="First name:" position="top">
        <e-input v-model="name.firstName" name="firstname" placeholder="..." />
      </e-label>
      <e-label name="Last name:" position="left">
        <e-input v-model="name.lastName" name="lastname" placeholder="..."/>
      </e-label>
      <e-label name="Street:" position="top" state="error">
        <e-input v-model="name.street"
                 name="street"
                 placeholder="..."
                 state="error"
                 notification="this is the error message"
        />
      </e-label>
      <e-label name="Notes:" position="top" state="info">
        <e-input v-model="name.notes"
                 name="notes"
                 placeholder="your notes"
                 state="info"
                 notification="this is the info message<br/>this is the info message<br/>this is the info message<br/>this is the info message<br/>this is the info message<br/>"
        />
      </e-label>
      <e-label name="Notes2:" position="top" state="success">
        <e-input v-model="name.notes2"
                 name="notes2"
                 placeholder="your notes"
                 state="success"
        />
      </e-label>
      <p>Your name is: <strong>{{ name.firstName }} {{ name.lastName }}</strong></p>
      <pre>{{ name }}</pre>

      <h2>e-checkbox</h2>
      <e-checkbox
        v-model="checkbox.checked"
        :name="checkbox.name"
        :value="checkbox.value"
        :display-name="checkbox.value"/>

    </form>
  </div>
</template>

<script>
  export default {
    name: 'forms',
    data() {
      return {
        name: {
          firstName: '',
          lastName: '',
          street: ''
        },
        checkbox: {
          checked: false,
          name: 'checkbox',
          value: 'Hello world...'
        }
      };
    }
  };
</script>

<style lang="scss">
  .forms {
    padding: $spacing--50;

    .e-label {
      margin-bottom: $spacing--10;
    }
  }
</style>
