<template>
  <div v-if="visible" class="confirm-overlay" @click.self="handleCancel">
    <div class="confirm-dialog">
      <h3 class="confirm-title">{{ title }}</h3>
      <p class="confirm-message">{{ message }}</p>
      <div class="confirm-actions">
        <button class="confirm-btn cancel" @click="handleCancel">取消</button>
        <button class="confirm-btn confirm" @click="handleConfirm">确定</button>
      </div>
    </div>
  </div>
</template>

<script setup>
const props = defineProps({
  visible: {
    type: Boolean,
    default: false
  },
  title: {
    type: String,
    default: '确认操作'
  },
  message: {
    type: String,
    default: '确定要执行此操作吗？'
  }
})

const emit = defineEmits(['confirm', 'cancel'])

const handleConfirm = () => {
  emit('confirm')
}

const handleCancel = () => {
  emit('cancel')
}
</script>

<style scoped>
.confirm-overlay {
  position: fixed;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: rgba(0, 0, 0, 0.5);
  display: flex;
  align-items: center;
  justify-content: center;
  z-index: 1000;
}

.confirm-dialog {
  background: white;
  border-radius: 12px;
  padding: 30px;
  max-width: 400px;
  width: 90%;
  box-shadow: 0 10px 40px rgba(0, 0, 0, 0.2);
}

.confirm-title {
  margin: 0 0 15px 0;
  color: #333;
  font-size: 1.2rem;
}

.confirm-message {
  margin: 0 0 25px 0;
  color: #666;
  font-size: 1rem;
  line-height: 1.6;
}

.confirm-actions {
  display: flex;
  gap: 10px;
  justify-content: flex-end;
}

.confirm-btn {
  padding: 10px 20px;
  border: none;
  border-radius: 6px;
  font-size: 1rem;
  cursor: pointer;
  transition: all 0.3s;
}

.confirm-btn.confirm {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
}

.confirm-btn.confirm:hover {
  opacity: 0.9;
}

.confirm-btn.cancel {
  background: #f0f0f0;
  color: #666;
}

.confirm-btn.cancel:hover {
  background: #e0e0e0;
}
</style>
