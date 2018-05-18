## vue-pagination分页组件

用于Vue 2的分页组件，组件样式使用Bootstrap定义的[分页](http://v3.bootcss.com/components/#pagination)类。

### 使用示例 

```html
<template>
  <div>
      <Pagination 
        :total-pages="totalPages" 
        :current-page="currentPage" 
        @pagechanged="onPageChange"
      ></Pagination>
  </div>
</template>

<script>
import Pagination from "./Pagination";
export default {
  components: {
    Pagination
  },
  data() {
    return {
      totalRecord: 123,
      pageSize: 10
    };
  },
  computed: {
    totalPages() {
      return Math.ceil(this.totalRecord / this.pageSize);
    }
  },
  methods: {
    // 监听切换页码的事件
    onPageChange: function(page) {
      console.log(page);
    }
  }
};
</script>
```