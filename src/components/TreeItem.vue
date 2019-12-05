<template>
  <div>
    <div
      class="flex items-center rounded-sm p-1 mx-2 hover:bg-gray-700 mb-1 drag-area"
      :disabled="data.disabled"
      v-bind:class="{ draggable: !data.disabled }"
    >
      <button
        class="flex focus:outline-none focus:shadow-none"
        @click.prevent="isOpen = !isOpen"
      >
        <icon
          :name="isOpen ? 'triangle-down' : 'triangle-right'"
          size="12"
          class="mr-1"
          :class="{ 'opacity-0': !children.length }"
        />
      </button>

      <icon
        :name="items[data.name].icon || 'div'"
        size="12"
        color="CapeCod"
        class="mr-1"
      />
      <span class="text-xs text-gray-200">{{
        items[data.name].name || data.name
      }}</span>
    </div>

    <draggable
      class="ml-1"
      :list="children"
      :group="{ name: 'g1' }"
      tag="div"
    >
      <tree-item
        v-for="(item, index) in children"
        :key="index"
        :data="item"
        :hidden="!isOpen"
      />
    </draggable>
  </div>
</template>
<script>
import draggable from "vuedraggable";
import Icon from "./Icon";

export default {
  name: "tree-item",

  components: {
    Icon,
    draggable
  },

  computed: {
    children() {
      return this.data.items || [];
    }
  },

  props: {
    data: {
      type: Object,
      required: false,
      default: () => ({})
    }
  },

  data() {
    return {
      isOpen: true,
      items: {
        body: {
          icon: "layout",
          name: "Body"
        },
        div: {
          icon: "div",
          name: "Div block"
        },
        h1: {
          icon: "heading",
          name: "Heading"
        },
        p: {
          icon: "paragraph",
          name: "Paragraph"
        },
        button: {
          icon: "pointer",
          name: "Button"
        }
      }
    };
  }
};
</script>

<style>
.activeItem {
  @apply bg-gray-600;
}
.activeItem:hover {
  @apply bg-gray-600;
}
.activeItem svg #CapeCod {
  fill: #b0b2b2;
}

.draggable {
  cursor: move;
}
</style>
