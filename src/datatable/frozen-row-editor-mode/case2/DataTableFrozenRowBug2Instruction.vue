<template>
  <div>
    <div>
      <div>Given:</div>
      <ol>
        <li>
          in my `@cell-edit-complete` function, there are codes: <br/>
          <code>
            const { data, newValue, field } = event; <br/>
            data[field] = newValue;
          </code>
        </li>
      </ol>
    </div>
    <div>
      <div>When:</div>
      <ol>
        <li>click first cell of the first frozen row</li>
        <li>click first cell of the first non-frozen row</li>
        <li>click first cell of the first non-frozen row again</li>
      </ol>
    </div>
    <div>
      <div>Unexpected result:</div>
      <ol>
        <li>`DataTableCellEditCompleteEvent` was fired with unexpected `value` and `newValue`. `value` = "Name 1",
          `newValue` = "name of Frozen Row"
        </li>
      </ol>
    </div>
  </div>
</template>
<script>
export default {
  name: 'DataTableFrozenRowBug1Instruction'
}
</script>