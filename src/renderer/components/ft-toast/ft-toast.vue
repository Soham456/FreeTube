<template>
  <div class="toast-holder">
    <div
      v-for="toast in toasts"
      :key="toast.id"
      class="toast"
      :class="{ closed: !toast.isOpen, open: toast.isOpen }"
      tabindex="0"
      role="status"
    >
      <p class="message">
        {{ toast.message }}
      </p>
      <!-- Action Button (display only if there is an action) -->
      <button
        v-if="toast.btnName"
        class="action-button"
        @click.prevent="performAction(toast.id)"
      >
        {{ toast.btnName }}
      </button>
    </div>
  </div>
</template>

<script src="./ft-toast.js" />
<style scoped src="./ft-toast.css" />
