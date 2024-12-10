<template>
  <div id="app">
    <h1>Welkom in mijn Vue App</h1>
    <DirectivesExample/>
    <TestComputed/>
    <DynamicCheckList/>
    <LoginStatus/>
    <TempConverter/>
    <RealtimeZoekfunctie/>
    <GptOefeningen/>

  </div>
</template>
<script>
import {defineComponent} from "vue";
import DirectivesExample from "@/components/DirectiveExample.vue";
import TestComputed from "@/components/TestComputed.vue";
import DynamicCheckList from "@/components/DynamicCheckList.vue";
import LoginStatus from "@/components/LoginStatus.vue";
import TempConverter from "@/components/TempConverter.vue"
import RealtimeZoekfunctie from "@/components/RealtimeZoekfunctie.vue";
import GptOefeningen from "@/components/GptOefeningen.vue";

export default defineComponent({
  name:'App', //naam van het rootcomponent
  components:{
    GptOefeningen,
    RealtimeZoekfunctie,
    DirectivesExample,
    TestComputed,
    DynamicCheckList,
    LoginStatus,
    TempConverter,
  }
})

</script>