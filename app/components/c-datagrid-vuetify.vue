<template>
  <div :class="b()">
    <v-text-field
      v-model="gridOptions.search"
      append-icon="search"
      label="Search"
      single-line
      hide-details
    />
    <v-data-table
      v-model="selected"
      v-bind="gridOptions"
      select-all
      item-key="name"
    >
      <template slot="items" slot-scope="props">
        <tr :active="props.selected" @click="props.selected = !props.selected">
          <td>
            <v-checkbox
              :input-value="props.selected"
              primary
              hide-details
            />
          </td>
          <td class="text-xs-left">{{ props.item.name }}</td>
          <td class="text-xs-left">{{ props.item.email }}</td>
          <td class="text-xs-left">{{ props.item.role }}</td>
          <td class="text-xs-left">{{ props.item.state }}</td>
          <td class="text-xs-left">{{ props.item.approved }}</td>
          <td class="text-xs-left">{{ props.item.documents }}</td>
          <td class="text-xs-left">{{ props.item.edited }}</td>
        </tr>
      </template>
      <div slot="no-results" :value="true">
        Your search for "{{ gridOptions.search }}" found no results.
      </div>
    </v-data-table>
  </div>
</template>

<script>
  import VCheckbox from 'vuetify/es5/components/VCheckbox';
  import VAlert from 'vuetify/es5/components/VAlert';
  import VTextField from 'vuetify/es5/components/VTextField';
  import { VDataTable } from 'vuetify/es5/components/VDataTable';

  export default {
    name: 'c-datagrid-vuetify',
    components: {
      VDataTable,
      VCheckbox,
      VTextField,
      VAlert,
    },
    // mixins: [],

    // props: {},
    data() {
      return {
        selected: [],
        gridOptions: {
          search: '',
          customFilter: (items, search, filter) => {
            search = search.toString().toLowerCase();

            return items.filter(row => filter(row['email'], search));
          },
          headers: [
            {
              text: 'Name',
              align: 'left',
              value: 'name'
            }, {
              text: 'Email',
              value: 'email'
            }, {
              text: 'Role',
              value: 'role'
            }, {
              text: 'State',
              value: 'state'
            }, {
              text: 'Approved',
              value: 'approved',
            }, {
              text: 'Documents',
              value: 'documents'
            }, {
              text: 'Edited',
              value: 'edited',
            },
          ],
          items: [
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
        }
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
  .c-datagrid-vuetify {
  }

</style>
