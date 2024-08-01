<script setup lang="ts">
import DataTableFrozenRowBug1Instruction from "./DataTableFrozenRowBug1Instruction.vue";
import DataTableFrozenRowBug1Component from "./DataTableFrozenRowBug1Component.vue";
</script>

<template>
  <div style="border:1px solid red; padding: 1rem;">
    <h1>Show Case 1</h1>
    <DataTableFrozenRowBug1Instruction/>
    <b style="color:red">Please interact with the data table below:</b>
    <DataTableFrozenRowBug1Component/>
  </div>
</template>
