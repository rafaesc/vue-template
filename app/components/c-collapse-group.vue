<template>
  <div :class="b()">
    <!-- @slot Use this for multiple c-collapsible items -->
    <slot></slot>
  </div>
</template>

<script>
  import EventBus from '@/setup/event-bus';

  /**
   * Wrapper for multiple (c-collapse) itmes.
   */
  export default {
    name: 'c-collapse-group',
    // components: {},
    // mixins: [],

    props: {
      /**
       * Defines if items can be open simultaneously
       */
      oneActive: {
        type: Boolean,
        default: true,
      }
    },
    // data() {
    //   return {};
    // },

    // computed: {},
    // watch: {},

    // beforeCreate() {},
    // created() {},
    // beforeMount() {},
    mounted() {
      /**
       * Emits toggled event
       */
      EventBus.$on('c-collapse.toggled', (payload) => {
        const collapseComponent = payload.component; // child

        /**
         * Receives update from child and emits update to EventBus
         *
         * @event   c-collapse-group.toggle
         * @type      {object}  payload
         * @property  {object}  payload.component         Current c-collapse-group instance
         * @property  {object}  payload.toggleCollapse    Component instance of original event
         */
        if (this.$el.contains(collapseComponent.$el) && this.oneActive) {
          EventBus.$emit('c-collapse-group.toggle', { component: this, toggledCollapse: collapseComponent });
        }
      });
    },
    // beforeUpdate() {},
    // updated() {},
    // activated() {},
    // deactivated() {},
    // beforeDestroy() {},
    // destroyed() {},

    // methods: {},
    // render() {},
  };
</script>

