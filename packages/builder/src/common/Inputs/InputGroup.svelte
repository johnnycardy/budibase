<script>
  export let meta = [];
  export let size = '';
  export let values = [];
</script>

<div class="inputs {size}">
  {#each meta as { placeholder }, i}
    <input type="number" placeholder="{placeholder}" bind:value={values[i]}/>
  {/each}
</div>

<style>
.inputs {
    display: flex;
    justify-content: space-between;

  }

  input {
    width: 83px;
    font-size: 12px;
    font-weight: 700;
    color: #163057;
    opacity: 0.7;
    padding: 5px 10px;
    box-sizing: border-box;
    border: 1px solid #DBDBDB;
    border-radius: 2px;
    outline: none;
  }

  input[type=number]::-webkit-inner-spin-button,
  input[type=number]::-webkit-outer-spin-button {
    -webkit-appearance: none;
    -moz-appearance: none;
    appearance: none;
    margin: 0;
}

  .small > input {
    width: 38px;
    height: 38px;
    display: flex;
    justify-content: center;
    align-items: center;
    text-align: center;
    padding: 0;
  }

  .small > input::placeholder {
    text-align: center;
  }
</style>
