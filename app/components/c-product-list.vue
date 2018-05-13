<template>
  <div :class="b()">

  </div>
</template>

<script>
  import { mapGetters, mapActions } from 'vuex';

  export default {
    name: 'c-product-list',
    // components: {},
    // mixins: [],

    // props: {},
    // data() {
    //   return {};
    // },

    computed: {
      ...mapGetters({
        erp: 'product/erp',
      })
    },
    // watch: {},

    // beforeCreate() {},
    created() {
      this.fetchErp(['12345', '23456', '34567']);
    },
    // beforeMount() {},
    // mounted() {},
    // beforeUpdate() {},
    // updated() {},
    // activated() {},
    // deactivated() {},
    // beforeDestroy() {},
    // destroyed() {},

    methods: {
      ...mapActions({
        fetchErp: 'product/fetchErp',
      })
    },
    // render() {},
  };
</script>

<style lang="scss">
  .c-product-list {

  }
</style>
