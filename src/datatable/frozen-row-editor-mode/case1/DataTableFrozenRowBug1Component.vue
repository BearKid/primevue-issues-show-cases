<script setup lang="ts">
import {onMounted, ref} from 'vue';
import DataTable, {type DataTableCellEditCompleteEvent} from "primevue/datatable";
import Column from "primevue/column";

type MyRecord = {
  id: number,
  name: string,
  company: string
}

const getCustomersMedium = async (): Promise<MyRecord[]> => {
  return Promise.resolve(
      [
        {
          id: 1000,
          name: 'Name 1',
          company: 'company 1',

        },
        {
          id: 2000,
          name: 'Name 2',
          company: 'company 2',
        }
      ]
  );
}
const customers = ref<MyRecord[]>([]);
const lockedCustomers = ref<MyRecord[]>([
  {
    id: 3000,
    name: 'name of Frozen Row',
    company: 'company of Frozen Row',
  }
]);

onMounted(() => {
  getCustomersMedium().then((data) => {
    customers.value = data;
  });
});

const onCellEditComplete = (event: DataTableCellEditCompleteEvent) => {
  console.log(
      "onCellEditComplete>>\n",
      "event.value = ", event.value, "\n",
      "event.newValue = ", event.newValue, "\n",
      "event", event
  );
}

</script>

<template>
  <DataTable
      :value="customers"
      :frozenValue="lockedCustomers"
      :edit-mode="'cell'"
      @cell-edit-complete="onCellEditComplete"
      :pt="{
               bodyRow(options) {
                   return {
                     style: {
                       'font-weight': options.props.frozenRow ? 'bold' : 'normal',
                     }
                   }
               }
            }"
  >
    <Column field="name" header="Name">
      <template #body="{data, field, frozenRow, index}">
        View mode=>【{{ data[field] }}】【index：{{ index }}】【frozenRow：{{ frozenRow }}】
      </template>
      <template #editor="{ data, field, index, frozenRow}">
        <div>
          Edit mode =>【{{ data[field] }}】【index：{{ index }}】【frozenRow：{{ frozenRow }}】
        </div>
      </template>
    </Column>

    <Column field="company" header="Company">
      <template #body="{data, field, frozenRow, index}">
        View mode=>【{{ data[field] }}】【index：{{ index }}】【frozenRow：{{ frozenRow }}】
      </template>
      <template #editor="{ data, field, index, frozenRow}">
        <div>
          Edit mode =>【{{ data[field] }}】【index：{{ index }}】【frozenRow：{{ frozenRow }}】
        </div>
      </template>
    </Column>
  </DataTable>
</template>
