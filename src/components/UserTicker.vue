<template>
  <div class="glass-card ticker-card">
    <div class="ticker-wrapper">
      <div v-for="(item, index) in tickerItems" :key="index" class="ticker-item">
        <span>{{ item.text }}</span>
        <span style="color: var(--success-color); font-weight: bold;">[生成成功]</span>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref } from 'vue';

const tickerItems = ref([
  { text: '用户 138****8892 成功生成了 [玻尿酸水光精华液] 爆款主图文案' },
  { text: '用户 159****3104 成功合成了 [智能降噪耳机] 短视频前3秒脚本' },
  { text: '用户 186****6617 成功解析了 [低卡无糖黑巧] 直播间促单话术' },
  { text: '用户 135****9023 成功策划了 [极客电竞椅] 聚划算大促活动方案' },
  { text: '用户 173****5180 成功生成了 [法式优雅连衣裙] 小红书种草笔记' },
]);
</script>

<style scoped>
.ticker-card {
  padding: 0.6rem 1rem;
  margin-bottom: 1.25rem;
  overflow: hidden;
}

.ticker-wrapper {
  display: flex;
  gap: 2rem;
  white-space: nowrap;
  animation: ticker 25s linear infinite;
}

.ticker-wrapper:hover {
  animation-play-state: paused;
}

.ticker-item {
  display: inline-flex;
  align-items: center;
  gap: 0.5rem;
  font-size: 0.8rem;
  color: var(--text-secondary);
}

@keyframes ticker {
  0% {
    transform: translateX(100%);
  }
  100% {
    transform: translateX(-100%);
  }
}
</style>
