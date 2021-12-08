<template>
  <div>
    <div class="input-group-prepend">
      <div class="input-group-text" id="list1">
        <input type="checkbox" aria-label="Checkbox for following text input" />
        <input
          type="text"
          class="form-control disabled"
          aria-label="Text input with checkbox"
          :value="nama"
        />
      </div>
    </div>
  </div>
</template>
<script>
export default {
  props: {
    id: Number,
    nama: String,
    posisi: { type: String, default: "kiri" }
  }
};
</script>
