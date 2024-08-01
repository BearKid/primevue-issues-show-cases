<script setup lang="ts">
import DataTableFrozenRowBug2Instruction from "./DataTableFrozenRowBug2Instruction.vue";
import DataTableFrozenRowBug2Component from "./DataTableFrozenRowBug2Component.vue";
</script>

<template>
  <div style="border:1px solid green; padding: 1rem;">
    <h1>Show Case 2</h1>
    <DataTableFrozenRowBug2Instruction/>
    <b style="color:red">Please interact with the data table below:</b>
    <DataTableFrozenRowBug2Component/>
  </div>
</template>
