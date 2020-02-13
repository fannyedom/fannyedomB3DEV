<template>
    <fieldset class="input--block">
        <h3>
            <slot></slot>
        </h3>
        <label for="truc">
            <slot name="label"></slot>
        </label>
        <input name="truc"
               v-bind:value="value"
               v-bind:placeholder="placeholder"
               v-on:input="$emit('input', $event.target.value)"
        >
        <span>
            <slot name="message"></slot>
        </span>
    </fieldset>
</template>

<script>
export default {
  name: 'InputBlock',
  props: {
    value: String,
    placeholder: String
  }
}
</script>

<style scoped="scoped">
    .input--block > * {
    }
</style>
