<template>
  <div class="tdesign-demo-dropdown">
    <t-dropdown :options="options" :min-column-width="112" @click="clickHandler">
      <div class="tdesign-demo-dropdown-trigger">
        <t-button variant="text">
          <span class="tdesign-demo-dropdown__text"> 下拉菜单 <t-icon name="chevron-down" size="16" /> </span>
        </t-button>
      </div>
    </t-dropdown>
    <br/>
    <t-dropdown :min-column-width="88" trigger="click" @click="handleClick">
      <t-button variant="text"> 下拉菜单 </t-button>
      <template #dropdown>
        <t-dropdown-menu>
          <t-dropdown-item :value="1"> 操作一 </t-dropdown-item>
          <t-dropdown-item :value="2"> 操作二 </t-dropdown-item>
        </t-dropdown-menu>
      </template>
    </t-dropdown>
  </div>
</template>
<script setup>
import { MessagePlugin } from 'tdesign-vue-next';

const options = [
  {
    content: '操作一',
    value: 1,
  },
  {
    content: '操作二',
    value: 2,
  },
  {
    content: '操作三',
    value: 3,
  },
  {
    content: '操作四',
    value: 4,
  },
];

const clickHandler = (data) => {
  console.log('clickHandler', data);
  MessagePlugin.success(`选中【${data.content}】`);
};


const handleClick = (data, { e }) => {
  console.log('handleClick', data);
  e.preventDefault();
};
</script>
<style scoped>

.tdesign-demo-dropdown__text {
  display: inline-flex;
}
.t-icon {
  margin-left: 8px;
}
</style>