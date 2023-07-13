<template>
  <div>
    <div class="button-container">
      <v-btn
        color="primary"
        dark
        @click="openDialog"
      >
        Add Employee
      </v-btn>
      <v-dialog v-model="dialogVisible" max-width="500px">
        <v-card>
          <v-card-title>
            <span class="headline">Add Employee</span>
          </v-card-title>
          <v-card-text>
            <!-- Dialog content goes here -->
            This is the content of the dialog.
          </v-card-text>
          <v-card-actions>
            <v-btn color="primary" @click="save">Save</v-btn>
            <v-btn color="secondary" @click="cancel">Cancel</v-btn>
          </v-card-actions>
        </v-card>
      </v-dialog>
    </div>
    <div>
      <v-data-table
        :headers="headers"
        :items="EmpDetails"
        :items-per-page="5"
        class="elevation-1"
      ></v-data-table>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'DataTable',

    data () {
      return {
        dialogVisible: false,
        headers: [
          {
            text: 'Employee Name',
            align: 'start',
            sortable: false,
            value: 'empname',
          },
          { text: 'Employee ID', value: 'empId', sortable: false},
          { text: 'Mail ID', value: 'empMailId', sortable: false, },
          { text: 'Designation', value: 'designation', sortable: false, },
          { text: 'DOJ', value: 'doj', sortable: false, },
        ],
        EmpDetails: [
          {
            empname: 'John Doe',
            empId: 'taSki7',
            empMailId: 'john.doe@taski.in',
            designation: 'Junior Developer',
            doj: '01-01-2001',
          },
          
        ],
      }
    },
    methods: {
      openDialog() {
        this.dialogVisible = true; //Open the dialog
        console.log("Open Dialog is Clicked", this.dialogVisible)
      },
      save() {
        this.dialogVisible = false; //Close the dialog
      },
      cancel() {
        this.dialogVisible = false; //Close the dialog
      }
    }
  }
</script>

<style>
  .button-container {

    display: flex;
    justify-content: end;
    margin: 16px;
  }
</style>