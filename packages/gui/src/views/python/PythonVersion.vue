<template>
  <div>
    <a-form
      layout="horizontal"
      :label-col="{ span: 3 }"
      :wrapper-col="{ span: 16 }"
      labelAlign="left"
    >
      <a-form-item label="镜像源">
        <a-select v-model="currentPythonMirror">
          <a-select-option v-for="mirror in pythonMirrors" :key="mirror.id">
            {{ mirror.name }}
          </a-select-option>
        </a-select>
      </a-form-item>
      <a-form-item label="安装目录">
        <a-input />
      </a-form-item>
      <a-form-item label="缓存目录">
        <a-input />
      </a-form-item>
    </a-form>

    <a-table
      :columns="columns"
      :data-source="data"
      :scroll="{ y: 480 }"
      :pagination="false"
    >
      <template slot="action" slot-scope="text, record, index">
        <span v-if="index == 1">
          <a href="javascript:;">卸载</a>
        </span>
        <span v-else> 使用 </span>
      </template>
    </a-table>
  </div>
</template>
<script>
const columns = [
  {
    title: '版本',
    dataIndex: 'version',
  }, {
    title: '操作',
    key: 'action',
    scopedSlots: { customRender: 'action' },
  },
];

const data = [];
for (let i = 0; i < 10; i++) {
  data.push({
    key: i,
    version: `python ${i}`,
    address: `London, Park Lane no. ${i}`,
  });
}
export default {
  data () {
    return {
      data,
      columns,
      currentPythonMirror: ["huawei"],
      pythonMirrors: [
        {
          id: "huawei",
          name: "华为云",
          mirror: "https://repo.huaweicloud.com/python"
        }
      ]
    };
  },
  methods: {
    handleMirrorChange (key) {
      this.currentPythonMirror = key;
    }
  },
};
</script>
