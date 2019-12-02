<template>
  <div id="app">
    <div class="flex-none bg-gray-800 w-64">
      <div
        class="text-white p-3 mb-2 border-b border-gray-700 font-medium text-base tracking-wide"
      >
        Layers
        <button
          class="close-icon p-2 focus:outline-none focus:shadow-none float-right"
        >
          <icon name="x" color="CapeCod" size="12"></icon>
        </button>
      </div>

      <tree-item :data="data" class="h-full overflow-scroll pb-32" />
    </div>
  </div>
</template>

<script>
import Icon from "./components/Icon.vue";
import TreeItem from "./components/TreeItem.vue";

export default {
  name: "app",
  components: {
    Icon,
    TreeItem
  },
  data() {
    return {
      data: {
        name: "body",
        className: "p-10 xl:p-20",
        items: [
          {
            name: "div",
            className: "",
            items: [
              {
                name: "h1",
                className: "text-3xl font-bold",
                text: "Welcome back, Ignas!"
              },
              {
                name: "p",
                className: "text-lg text-gray-500 tracking-wide mb-10",
                text:
                  "You have learned 80% of the course. Keep it up and improve your results!"
              },
              {
                name: "h1",
                className: "text-xl font-semibold mb-5",
                text: "Your next classes"
              }
            ]
          },
          {
            name: "div",
            className: "flex -mx-4",
            items: [
              {
                name: "div",
                className: "flex-1 flex bg-blue-500 p-6 rounded-lg mx-4",
                items: [
                  {
                    name: "div",
                    className:
                      "bg-blue-400 h-12 w-12 flex items-center justify-center rounded-lg mr-4",
                    items: [
                      {
                        name: "h1",
                        className: "text-lg font-bold text-white",
                        text: "B2"
                      }
                    ]
                  },
                  {
                    name: "div",
                    className: "",
                    items: [
                      {
                        name: "p",
                        className: "text-white opacity-75 font-medium",
                        text: "Business English"
                      },
                      {
                        name: "h1",
                        className: "text-xl text-white font-bold",
                        text: "Grammar"
                      }
                    ]
                  }
                ]
              },
              {
                name: "div",
                className: "flex-1 flex bg-blue-500 p-6 rounded-lg mx-4",
                items: [
                  {
                    name: "div",
                    className:
                      "bg-blue-400 h-12 w-12 flex items-center justify-center rounded-lg mr-4",
                    items: [
                      {
                        name: "h1",
                        className: "text-lg font-bold text-white",
                        text: "B2"
                      }
                    ]
                  },
                  {
                    name: "div",
                    className: "",
                    items: [
                      {
                        name: "p",
                        className: "text-white opacity-75 font-medium",
                        text: "Business Spanish"
                      },
                      {
                        name: "h1",
                        className: "text-xl text-white font-bold",
                        text: "Vocabulary"
                      }
                    ]
                  }
                ]
              },
              {
                name: "div",
                className: "flex-1 flex bg-blue-500 p-6 rounded-lg mx-4",
                items: [
                  {
                    name: "div",
                    className:
                      "bg-blue-400 h-12 w-12 flex items-center justify-center rounded-lg mr-4",
                    items: [
                      {
                        name: "h1",
                        className: "text-lg font-bold text-white",
                        text: "B2"
                      }
                    ]
                  },
                  {
                    name: "div",
                    className: "",
                    items: [
                      {
                        name: "p",
                        className: "text-white opacity-75 font-medium",
                        text: "Business French"
                      },
                      {
                        name: "h1",
                        className: "text-xl text-white font-bold",
                        text: "Vocabulary"
                      }
                    ]
                  }
                ]
              }
            ]
          }
        ]
      }
    };
  }
};
</script>
