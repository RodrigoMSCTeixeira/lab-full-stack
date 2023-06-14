<template>
  <div>
    <form @submit.prevent="calculate">
      <fieldset>
        <select v-model="item.from">
          <option
            v-for="(unit, index) in absoluteLengths"
            :key="index"
            :value="unit"
          >
            {{ unit }}
          </option>
        </select>
        <input type="text" v-model="item.value" />
      </fieldset>

      <fieldset>
        <select v-model="item.to">
          <option
            v-for="(unit, index) in relativeLengths"
            :key="index"
            :value="unit"
          >
            {{ unit }}
          </option>
        </select>
        <input type="text" />
      </fieldset>

      <fieldset>
        <legend>Resultado</legend>
        <input type="text" v-model="item.result" />
      </fieldset>

      <button>Conveter</button>
    </form>
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "CssUnits",
  data: () => ({
    item: {
      from: "",
      to: "",
      value: "",
      result: "",
    },
    absoluteLengths: ["cm", "mm", "in", "px", "pt", "pc"],
    relativeLengths: ["em", "ex", "ch", "rem", "vw", "vh", "vmin", "vmax", "%"],
  }),
  methods: {
    calculate() {
      console.log(this.item);
      this.item.result = this.convert(
        this.item.to,
        this.item.from,
        this.item.value
      );
    },

    convert: (to: string, from: string, value: string) => {
      let lenght = 0;
      let result = 0;

      switch (to) {
        case "cm":
          lenght = parseFloat(value) / 1;
          break;
        case "mm":
          lenght = parseFloat(value) / 10;
          break;
        case "in":
          break;
        case "px":
          break;
        case "pt":
          break;
        case "pc":
          break;
      }

      switch (from) {
        case "em":
          break;
        case "ex":
          break;
        case "ch":
          break;
        case "rem":
          result = lenght * 2.3622050220101;
          break;
        case "vw":
          break;
        case "vh":
          break;
        case "vmin":
          break;
        case "vmax":
          break;
        case "%":
          break;
      }

      return result.toLocaleString("pt-BR");
    },
  },
});
</script>
