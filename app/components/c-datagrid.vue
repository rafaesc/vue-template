<template>
  <div :class="b()">
    <h2>Data-Grid:</h2>
    <dx-data-grid v-bind="gridOptions">
      <div slot="cell-role" slot-scope="data">
        <select>
          <option v-for="role in roles"
                  :key="role.key"
                  :selected="role.key === data.value"
                  value="role.key"
          >
            {{ role.label }}
          </option>
        </select>
      </div>
    </dx-data-grid>
    <a href="https://js.devexpress.com/Documentation/ApiReference/UI_Widgets/dxDataGrid/" target="_blank">
      Datagrid API
    </a>
  </div>
</template>

<script>
  import { DxDataGrid } from 'devextreme-vue';

  export default {
    name: 'c-datagrid',
    components: {
      DxDataGrid,
    },
    // mixins: [],

    // props: {},
    data() {
      return {
        roles: [
          {
            label: 'User',
            key: 'user',
          },
          {
            label: 'Administrator',
            key: 'admin',
          },
        ],
        gridOptions: {
          columnHidingEnabled: true,
          columnAutoWidth: true,
          dataSource: [
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
          searchPanel: {
            visible: true,
          },
          allowColumnResizing: true,
          paging: {
            pageSize: 10,
          },
          pager: {
            showInfo: true,
            showNavigationButtons: true,
            showPageSizeSelector: true,
          },
          filterRow: {
            visible: true,
          },
          editing: {
            allowAdding: true,
            allowUpdating: true,
            allowDeleting: true,
            mode: 'row',
          },
          selection: {
            mode: 'multiple',
            showCheckBoxesMode: 'always',
          },
          columns: [
            {
              dataField: 'name',
              caption: 'Anzeige Namen',
              fixed: true,
              fixedPosition: 'left',
            },
            {
              dataField: 'email',
              caption: 'Email',
            },
            {
              dataField: 'role',
              caption: 'Benutzerrolle',
              /* eslint-disable quotes */
              cellTemplate: "cell-role", // has to be double quotes, otherwise it won't work.
            },
            {
              dataField: 'state',
              caption: 'Status',
            },
            {
              dataField: 'approved',
              caption: 'Fregegeben',
            },
            {
              dataField: 'documents',
              caption: 'Dokumente',
            },
            {
              dataField: 'edited',
              dataType: 'datetime',
              caption: 'Editiert',
              format: 'dd.MM.yyyy'
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
  .c-datagrid {
  }

</style>
