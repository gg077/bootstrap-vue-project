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
    <FetchData/>
    <TimerCleanup/>
    <BeforeUpdate/>

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
import FetchData from "@/components/FetchData.vue";
import TimerCleanup from "@/components/TimerCleanup.vue";
import BeforeUpdate from "@/components/BeforeUpdate.vue";



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
    FetchData,
    TimerCleanup,
    BeforeUpdate,
  }
})

</script>