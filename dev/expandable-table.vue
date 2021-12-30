<template>
  <div>
    <vue-good-table :columns="columns" :rows="rows" :pagination-options="{
      enabled: true,
      perPage: 3,
      perPageDropdown: [3, 5, 10, 20],
      dropdownAllowAll: false,
    }">
      <template v-slot:table-row="{ toggleExpand, column, formattedRow }"
        ><div @click="toggleExpand">
          {{ formattedRow[column.field] }}
        </div></template
      >
      <template v-slot:table-line-expanded="props">
        Props: {{ props }}</template
      >
    </vue-good-table>
  </div>
</template>

<script>
export default {
  name: "expandable-table",
  data() {
    return {
      columns: [
        {
          label: "Name",
          field: "name",
        },
        {
          label: "Age",
          field: "age",
          type: "number",
        },
        {
          label: "Created On",
          field: "createdAt",
          type: "date",
          dateInputFormat: "yyyy-MM-dd",
          dateOutputFormat: "MMM do yy",
        },
        {
          label: "Percent",
          field: "score",
          type: "percentage",
        },
      ],
      rows: [
        { id: 1, name: "John", age: 20, createdAt: "", score: 0.03343 },
        {
          id: 2,
          name: "Jane",
          age: 24,
          createdAt: "2011-10-31",
          score: 0.03343,
        },
        {
          id: 3,
          name: "Susan",
          age: 16,
          createdAt: "2011-10-30",
          score: 0.03343,
        },
        {
          id: 4,
          name: "Chris",
          age: 55,
          createdAt: "2011-10-11",
          score: 0.03343,
        },
        {
          id: 5,
          name: "Dan",
          age: 40,
          createdAt: "2011-10-21",
          score: 0.03343,
        },
        {
          id: 6,
          name: "John",
          age: 20,
          createdAt: "2011-10-31",
          score: 0.03343,
        },
      ],
    };
  },
};
</script>
