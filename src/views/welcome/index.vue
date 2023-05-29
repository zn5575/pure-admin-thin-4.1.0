<script setup lang="ts">
import { getUser } from "@/api/user";
import { ref } from "vue";

defineOptions({
  name: "Welcome"
});
const loading = ref(false);
const res1 = ref("");

const onGetUser = async () => {
  loading.value = true;
  setTimeout(() => console.log("wait 1s"), 1000);
  const res = await getUser();
  console.log(res);
  res1.value = res.username;
};
</script>

<template>
  <h1>Pure-Admin-Thin（非国际化版本）</h1>
  <el-button type="success" @click="onGetUser">
    测试getuser功能：{{ res1 }}
  </el-button>
</template>
