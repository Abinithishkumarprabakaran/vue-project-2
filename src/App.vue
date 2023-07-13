<template>
  <v-app>
    <!-- <DataTable /> -->
    <EmployeeDetails />
  </v-app>
</template>

<script>
// import DataTable from './components/DataTable';
import EmployeeDetails from './components/EmployeeDetails.vue';

export default {
  name: 'App',

  components: {
    // DataTable,
    EmployeeDetails,
  },

  data: () => ({
    //
  }),
};
</script>
