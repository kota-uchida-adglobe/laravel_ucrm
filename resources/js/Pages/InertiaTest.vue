<script setup>
import { Link } from '@inertiajs/inertia-vue3'
import { ref } from 'vue'

const newTitle = ref("")
const newContent = ref("")
</script>

<template>
  <h1>Inertiaテストです</h1><br>
  <a href="/">aタグで移動</a><br>
  <Link href="/">Linkで移動</Link><br>
  <Link :href="route('inertia.index')">名前付きルートの確認</Link><br>
  <Link :href="route('inertia.show', { id: 10 })">ルートパラメータの確認</Link>

  <div class="mb-8"></div>
  <input type="text" name="title" v-model="newTitle">{{ newTitle }}<br>
  <input type="text" name="content" v-model="newContent">{{ newContent }}<br>
  <Link as="button" method="POST" :href="route('inertia.store')"
  :data="{title: newTitle, content: newContent}">保存</Link>
</template>