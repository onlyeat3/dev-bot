<template>
  <div>
    <a-tabs default-active-key="1" tabPosition="left">
      <a-tab-pane key="1" tab="版本管理">
        <python-version></python-version>
      </a-tab-pane>
      <a-tab-pane key="2" tab="环境管理" force-render>
        <div></div>
      </a-tab-pane>
    </a-tabs>
  </div>
</template>
<script>
import PythonVersion from './PythonVersion.vue'
export default {
  components: { PythonVersion },
  data () {
    return {
    };
  },
  methods: {
  },
};
</script>
