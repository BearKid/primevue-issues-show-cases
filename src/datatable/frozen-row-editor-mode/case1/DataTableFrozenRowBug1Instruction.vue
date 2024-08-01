<template>
  <div>
    <div>
      <b>Sub case 1</b>
      <div>
        <div>
          <div>Given:</div>
          <ol>
            <li>there is no codes to update value in my `@cell-edit-complete` function, just logs the event in
              console.
            </li>
          </ol>
        </div>
        <div>When:</div>
        <ol>
          <li>click the first cell of second non-frozen row</li>
          <li>click the first cell of first frozen row</li>
          <li>click the second cell of first non-frozen row</li>
        </ol>
      </div>
      <div>
        <div>Unexpected result:</div>
        <ol>
          <li>the value of the second cell of the first non-frozen row was changed to cell value of the frozen row</li>
        </ol>
      </div>
    </div>

    <div>
      <b>Sub case 2</b>
      <div>
        <div>
          <div>Given:</div>
          <ol>
            <li>there is no codes to update value in my `@cell-edit-complete` function, just logs the event in
              console.
            </li>
          </ol>
        </div>
        <div>When:</div>
        <ol>
          <li>click the first cell of first non-frozen row</li>
          <li>click the second cell of first non-frozen row</li>
          <li>click the first cell of first frozen row</li>
        </ol>
      </div>
      <div>
        <div>Unexpected result:</div>
        <ol>
          <li>the first cell value of the frozen row was changed to the first cell value of the first non-frozen row
          </li>
        </ol>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: 'BugPage0Instruction'
}
</script>