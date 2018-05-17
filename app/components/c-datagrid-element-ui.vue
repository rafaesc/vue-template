<template>
  <div :class="b()">
    <el-table v-bind="gridOptions">
      <el-table-column type="selection" width="55"/>
      <el-table-column prop="name" sortable label="Name" width="180"/>
      <el-table-column prop="email" sortable label="Email"/>
      <el-table-column prop="role" label="Role"/>
      <el-table-column prop="state" label="State"/>
      <el-table-column prop="approved" label="Approved"/>
      <el-table-column prop="documents" label="Documents"/>
      <el-table-column prop="edited" label="Edited"/>
    </el-table>
  </div>
</template>

<script>
  import { Table, TableColumn } from 'element-ui';

  export default {
    name: 'c-datagrid-element-ui',
    components: {
      ElTable: Table,
      ElTableColumn: TableColumn,
    },
    // mixins: [],

    // props: {},
    data() {
      return {
        gridOptions: {
          showSummary: true,
          data: [
            {
              name: 'Claudio Schäpper',
              email: 'claudio.schäpper@cec.valantic.com',
              role: 'user',
              state: 'open',
              approved: true,
              documents: 'test.jpg',
              edited: '12-05-2018',
            }, {
              name: 'Mathias Ober',
              email: 'mathias.ober@cec.valantic.com',
              role: 'user',
              state: 'open',
              approved: true,
              documents: 'test.jpg',
              edited: '13-05-2018',
            }, {
              name: 'Patric Eberle',
              email: 'patric.eberle@cec.valantic.com',
              role: 'admin',
              state: 'open',
              approved: true,
              documents: 'test.jpg',
              edited: '01-05-2018',
            }, {
              name: 'Silvan Baumann',
              email: 'silvan.baumann@cec.valantic.com',
              role: 'user',
              state: 'open',
              approved: true,
              documents: 'test.jpg',
              edited: '12-05-2018',
            }, {
              name: 'Cheryl Oberholzer',
              email: 'cheryl.oberholzer@cec.valantic.com',
              role: 'user',
              state: 'open',
              approved: true,
              documents: 'test.jpg',
              edited: '04-04-2018',
            }, {
              name: 'Christoph Hirschbühl',
              email: 'christoph.hirschbühl@cec.valantic.com',
              role: 'user',
              state: 'open',
              approved: true,
              documents: 'test.jpg',
              edited: '12-11-2017',
            }, {
              name: 'Test User',
              email: 'test.user@somedomain.com',
              role: 'user',
              state: 'open',
              approved: true,
              documents: 'test.jpg',
              edited: '24-05-2018',
            }, {
              name: 'Bruce Willis',
              email: 'bruce.willis@somedomain.com',
              role: 'user',
              state: 'open',
              approved: true,
              documents: 'test.jpg',
              edited: '12-05-2018',
            }, {
              name: 'Bruce Wayne',
              email: 'bruce.wayne@somedomain.com',
              role: 'user',
              state: 'open',
              approved: true,
              documents: 'test.jpg',
              edited: '12-05-2018',
            }, {
              name: 'Chuck Norris',
              email: 'chuck.norris@somedomain.com',
              role: 'user',
              state: 'open',
              approved: true,
              documents: 'test.jpg',
              edited: '12-05-2018',
            }, {
              name: 'Jason Bourne',
              email: 'bourne@indenti.ty',
              role: 'user',
              state: 'open',
              approved: true,
              documents: 'test.jpg',
              edited: '12-09-2016',
            }, {
              name: 'Lionel Messi',
              email: 'leo.messi@somedomain.ar',
              role: 'user',
              state: 'open',
              approved: true,
              documents: 'test.jpg',
              edited: '12-05-2018',
            }, {
              name: 'Max Mustermann',
              email: 'max.musti@somedomain.com',
              role: 'user',
              state: 'open',
              approved: true,
              documents: 'test.jpg',
              edited: '12-05-2018',
            }, {
              name: 'Jennifer Lopez',
              email: 'lopez@j.lo',
              role: 'user',
              state: 'open',
              approved: true,
              documents: 'test.jpg',
              edited: '12-10-2015',
            }, {
              name: 'Morgan Freeman',
              email: 'dear@god.com',
              role: 'user',
              state: 'open',
              approved: true,
              documents: 'test.jpg',
              edited: '01-01-1970',
            },
          ],
        },
      };
    },

    // computed: {},
    // watch: {},

    // beforeCreate() {},
    // created() {},
    // beforeMount() {},
    // mounted() {},
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

<style lang="scss">
  .c-datagrid-element-ui {
  }
</style>
