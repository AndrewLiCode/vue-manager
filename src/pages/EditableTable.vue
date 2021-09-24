<template>
  <VmTable
    title="Editable Table"
    type="edit"
    :columns="dataColumns"
    :data="dataTable"
    v-on:add-ok="add"
    v-on:edit-ok="edit"
    v-on:delete-ok="deletefn"
    class="vm-margin"
  >
  </VmTable>
</template>

<script>
import VmTable from "@/components/vm-table";
export default {
  name: "EditableTable",
  components: {
    VmTable,
  },
  methods: {
    add: function (data) {
      this.dataTable.unshift(data);
    },
    edit: function (data) {
      this.dataTable.forEach(function (elem) {
        if (elem.id === data.id) {
          for (let i in data) {
            elem[i] = data[i];
          }
        }
      });
    },
    deletefn: function (data) {
      for (let i = 0; i < this.dataTable.length; i++) {
        for (let j = 0; j < data.length; j++) {
          if (this.dataTable[i].id === data[j].id) {
            this.dataTable.splice(i, 1);
          }
        }
      }
    },
  },
  data() {
    return {
      dataColumns: [
        {
          id: "20156541",
          title: "No",
          key: "id",
        },
        {
          id: "20156542",
          title: "Name",
          key: "name",
        },
        {
          id: "20156543",
          title: "Age",
          key: "age",
        },
        {
          id: "20156544",
          title: "Address",
          key: "address",
        },
      ],
      dataTable: [
        {
          id: "65416843154",
          name: "David",
          age: 18,
          address: "4807 Fairway Drive, Fairfield, CA",
        },
        {
          id: "65416843654",
          name: "Rob",
          age: 25,
          address: "4108 Hayhurst Lane, West Bloomfield, MI",
        },
        {
          id: "65416843194",
          name: "Kevin",
          age: 30,
          address: "3826 Cambridge Court, Gilbert, AZ",
        },
        {
          id: "65416843150",
          name: "Ryan",
          age: 26,
          address: "651 Grant Street, Longview, TX",
        },
        {
          id: "65416843150",
          name: "Jason",
          age: 25,
          address: "3106 Hart Ridge Road, Saginaw, MI",
        },
        {
          id: "65416843114",
          name: "Daniel",
          age: 30,
          address: "3982 Euclid Avenue, San Luis Obispo, CA",
        },
        {
          id: "25416843154",
          name: "Steven",
          age: 30,
          address: "1091 Elk Street, Los Angeles, CA",
        },
        {
          id: "65456843154",
          name: "Justin",
          age: 26,
          address: "3461 Collins Avenue, Worthington, OH",
        },
        {
          id: "65416843114",
          name: "Eric",
          age: 25,
          address: "2044 Clay Lick Road, Aurora, CO",
        },
        {
          id: "65416343154",
          name: "Chris",
          age: 30,
          address: "4740 Simons Hollow Road, Pittston, PA",
        },
        {
          id: "65419843154",
          name: "Tyler",
          age: 26,
          address: "4204 Tenmile, El Cajon, CA",
        },
      ],
    };
  },
};
</script>
