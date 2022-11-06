<template>
  <span>
    {{ text }} &nbsp;
    <a-cascader
      v-model:value="value"
      placeholder="Please select"
      :options="options"
      @change="onChange"
    >
      <a href="#">选择门店</a>
    </a-cascader>
  </span>
</template>
<script lang="ts">
import { defineComponent, ref } from 'vue';
import type { CascaderProps } from 'ant-design-vue';
const options: CascaderProps['options'] = [
  {
    value: 'AllCountry',
    label: '全国',
  },
  {
    value: 'Shandong',
    label: '山东省',
    children: [
      {
        value: 'jinantianqiaonan',
        label: '济南天桥青银高速南站',
      },
      {
        value: 'jinantianqiaobei',
        label: '济南天桥青银高速北站',
      },
      {
        value: 'liaochenggaotangnan',
        label: '聊城高唐青银高速南站',
      },
      {
        value: 'liaochenggaotangbei',
        label: '聊城高唐青银高速北站',
      },
    ],
  },
  {
    value: 'Zhejiang',
    label: '浙江省',
    children: [
      {
        value: 'huzhoudeqingnan',
        label: '湖州德清练杭高速南站',
      },
      {
        value: 'huzhoudeqingbei',
        label: '湖州德清练杭高速北站',
      },
    ],
  },
  {
    value: 'Others',
    label: '其他地区',
    children: [
      {
        value: 'SomeElse',
        label: '其他某门店',
      },
    ],
  },
];

export default defineComponent({
  setup() {
    const value = ref<string[]>([]);
    const text = ref<string>('Unselect');

    const onChange: CascaderProps['onChange'] = (_value, selectedOptions) => {
      text.value = selectedOptions.map(o => o.label).join(', ');
    };

    return {
      value,
      text,
      options,
      onChange,
    };
  },
});
</script>

