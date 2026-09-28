<script setup lang="ts">
import { computed } from "vue";

defineOptions({
  name: "Welcome"
});

const hour = new Date().getHours();
const greeting = computed(() => {
  if (hour < 6 || hour >= 22) return "夜深了";
  if (hour < 9) return "早上好";
  if (hour < 12) return "上午好";
  if (hour < 14) return "中午好";
  if (hour < 18) return "下午好";
  return "晚上好";
});

const username = "朋友";
</script>

<template>
  <main class="welcome-page">
    <section class="greeting-card" aria-label="问候">
      <span class="greeting-icon" aria-hidden="true">☀️</span>
      <div>
        <p class="greeting-title">{{ greeting }}，{{ username }}！</p>
        <p class="greeting-message">很高兴与你相遇，祝你今天心情愉快。</p>
      </div>
    </section>
  </main>
</template>

<style scoped>
.welcome-page {
  padding: 24px;
}

.greeting-card {
  display: flex;
  gap: 16px;
  align-items: center;
  max-width: 520px;
  padding: 24px;
  margin-top: 24px;
  background: var(--el-bg-color, #fff);
  border: 1px solid var(--el-border-color, #ebeef5);
  border-radius: 12px;
  box-shadow: 0 4px 16px rgb(0 0 0 / 5%);
}

.greeting-icon {
  font-size: 32px;
}

.greeting-title {
  margin: 0;
  font-size: 20px;
  font-weight: 600;
  color: var(--el-text-color-primary, #303133);
}

.greeting-message {
  margin: 8px 0 0;
  color: var(--el-text-color-secondary, #909399);
}
</style>
