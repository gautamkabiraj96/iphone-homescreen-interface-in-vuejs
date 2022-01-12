<template>
  <div>
    <div class="np-app-container">
      <div class="np-app-title">Notes</div>
      <div v-for="(note, n) in notesList" :key="n">
        <div class="np-saved-note">
          {{ note }}
        </div>
      </div>
      <div class="np-note-editor">
        <textarea
          placeholder="Type something..."
          v-model="noteData"
          @keyup.enter="saveNote"
          class="np-note-editor-area"
        />
        <div @click="saveNote" class="np-save-btn">Save</div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: "NotesView",
  data() {
    return {
      notesList: [],
      noteData: null,
    };
  },
  methods: {
    saveNote() {
      this.noteData && this.notesList.push(this.noteData);
      this.noteData = null;
    },
  },
};
</script>
<style>
.np-note-editor {
  font-size: 14px;
  position: absolute;
  bottom: 100px;
}
.np-note-editor-area {
  width: 200px;
  height: 100px;
  overflow: auto;
  resize: none;
  border: 1px solid #0059ff;
  border-radius: 4px;
  outline: none;
  padding: 4px;
  font-size: 16px;
}
.np-saved-note {
  font-size: 14px;
  border-bottom: 1px solid #eee;
  padding: 4px 0px;
}
.np-save-btn {
  float: right;
  margin-right: 25px;
  margin-top: 6px;
  cursor: pointer;
  color: #0059ff;
}
</style>