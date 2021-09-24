<template>
  <div class="basic-table vm-margin">
    <VmTable
      title="Basic Table"
      :columns="dataColumns"
      :data="dataTable"
    ></VmTable>
  </div>
</template>

<script>
import VmTable from "@/components/vm-table";
export default {
  name: "BasicTable",
  components: {
    VmTable,
  },
  data() {
    return {
      dataColumns: [
        {
          id: "2.140710",
          title: "No",
          key: "id",
          sortable: true,
        },
        {
          id: "2.140711",
          title: "Name",
          key: "name",
          sortable: true,
        },
        {
          id: "2.140712",
          title: "Age",
          key: "age",
          sortable: true,
        },
        {
          id: "2.140713",
          title: "Address",
          key: "address",
          sortable: true,
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
