<template>
  <div class="field-container flex mt-6">
    <div
      class="p-3 flex-shrink-0 bg-gray-900 mr-3 rounded-full shadow"
      :style="{
        backgroundColor: `${name == 'socialLinks' ? item.color : buttonBg}`,
      }"
    >
      <div
        class="w-6 h-6"
        :class="name == 'socialLinks' ? null : 'action'"
        v-html="require(`~/assets/icons/${item.name}.svg?include`)"
      ></div>
    </div>
    <div class="w-full">
      <input
        class="px-4 w-full h-12 bg-gray-200 placeholder-gray-600 rounded focus:outline-none"
        type="text"
        :aria-label="'Enter ' + item.label"
        :title="'Enter ' + item.label"
        v-model="type[index].value"
        :placeholder="item.placeholder"
      />
    </div>
    <button
      class="p-3 flex-shrink-0 outline-none"
      @click="removeAction(name, index)"
      :aria-label="'Remove ' + item.label"
    >
      <div
        class="w-6 h-6"
        v-html="require(`~/assets/icons/remove.svg?include`)"
      ></div>
    </button>
  </div>
</template>

<script>
export default {
  props: ['name', 'item', 'index', 'type', 'buttonBg', 'removeAction'],
}
</script>

<style></style>
