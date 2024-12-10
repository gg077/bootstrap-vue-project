<template>
  <div class="container mt-5">
    <h1>Directives Voorbeeld</h1>
    <div>
      <p v-text="text"></p>
      <div v-html="htmlContent"></div>
      <div class="form-check form-switch">
        <input @click="toggleVisibility" class="form-check-input" type="checkbox" role="switch" id="flexSwitchCheckChecked" checked>
        <label class="form-check-label" for="flexSwitchCheckChecked">Checked switch checkbox input</label>
      </div>
      <p v-show="isVisible" class="mt-3">Deze tekst is zichtbaar</p>
      <ul>
        <li v-for="(item, index) in items" :key="index">{{index+1}}.{{item}}</li>

      </ul>
    </div>
  </div>
</template>
<script>
import {ref} from "vue";

export default{
  setup(){
    const text = ref('Dit is een voorbeeld van een v-text');

    const htmlContent = ref('<strong>Html inhoud via v-html</strong>');

    const isVisible= ref(true);
    const items = ref(['appels', 'kersen', 'peren'])
    const toggleVisibility = () =>{
      isVisible.value = !isVisible.value;
    }
    return {text, htmlContent,isVisible, toggleVisibility, items}

  }

}
</script>