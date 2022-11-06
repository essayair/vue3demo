<template>
  <a-cascader
    v-model:value="value"
    placeholder="Please select"
    :options="options"
    style="width: 100%"
  >
    <template #displayRender="{ labels, selectedOptions }">
      <span v-for="(label, index) in labels" :key="selectedOptions[index].value">
        <span v-if="index === labels.length - 1">
          {{ label }} 
        </span>
        <span v-else>{{ label }} /</span>
      </span>
    </template>
  </a-cascader>
</template>

<script lang="ts">
import { defineComponent, ref } from 'vue';
import type { CascaderProps } from 'ant-design-vue';
const options: CascaderProps['options'] = [
    {
      value: 'allcountry',
      label: '全国',
    },
    {
      value: 'shandong',
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
      value: 'zhejiang',
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
      value: 'otherplaces',
      label: '其他地区',
      children: [
        {
          value: 'someelse',
          label: '其他某门店',
        },
      ],
    },
  ];

export default defineComponent({
  setup() {
    const handleAreaClick = (e: Event, label: string, option: CascaderProps['options']) => {
      e.stopPropagation();
      console.log('clicked', label, option);
    };

    return {
      value: ref<string[]>(['zhejiang', 'huzhoudeqingbei']),
      options,
      handleAreaClick,
    };
  },
});
</script>

