<template>
  <div class="index-page">
    <a-input-search
      v-model:value="searchText"
      placeholder="input search text"
      enter-button
      @search="onSearch"
    />
    <MyDivider />
    <a-tabs v-model:activeKey="activeKey" @change="onTabChange">
      <a-tab-pane key="post" tab="文章">
        <PostList :post-list="postList" />
      </a-tab-pane>
      <a-tab-pane key="picture" tab="图片">
        <PictureList :picture-list="pictureList" />
      </a-tab-pane>
      <a-tab-pane key="user" tab="用户">
        <UserList :user-list="userList" />
      </a-tab-pane>
    </a-tabs>
  </div>
</template>

<script setup lang="ts">
import { ref } from "vue";

const searchText = ref<string>("");
const activeKey = ref("post");

const onSearch = (value: string) => {
  alert(value);
};
</script>
