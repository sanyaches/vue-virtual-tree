# vue-virtual-tree
### Based on vue3 encapsulation, the tree component dedicated to large data volume, if the data volume is not large, using this component is a bit costly

English & [简体中文](README-CN.md)

## [Docs & Demo](https://lychub.github.io/vue-virtual-tree)


## How to use

```
npm i vue-virtual-tree
```

Global registration, but this will lose the type, if you use typescript, this method is not recommended
``` js
import { createApp } from 'vue';
import VirTree from 'vue-virtual-tree';

createApp(App).use(VirTree).mount('#app');

In components:
<vir-tree />
```


Partial registration, you can get a complete type
``` js
<template>
  <div class="demo">
    <a-button @click="selectedNode">获取选中节点</a-button>
    <vir-tree ref="virTree" :source="list" />
  </div>
</template>

<script lang="tsx">
  import {defineComponent, onMounted, ref} from 'vue';
  import { VirTree } from 'vue-virtual-tree';
  import {TreeInstance, TreeNodeOptions} from "vue-virtual-tree";

  export default defineComponent({
    name: 'BaseDemo',
    components: { VirTree },
    setup(props, {emit}) {
      return {
        list
      }
    }
  });
</script>

```