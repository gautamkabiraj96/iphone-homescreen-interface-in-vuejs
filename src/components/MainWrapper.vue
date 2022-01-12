<template>
  <div class="np-wrapper-container">
    <div v-if="selectedView == selectableViews.home">
      <HomeWidget />
    </div>
    <div v-if="selectedView == selectableViews.phone">
      <PhoneView />
    </div>
    <div v-if="selectedView == selectableViews.notes">
      <NotesView />
    </div>
    <div v-if="selectedView == selectableViews.gallery">
      <GalleryView />
    </div>
    <div v-if="selectedView == selectableViews.clock">
      <ClockView />
    </div>
    <div class="np-icons-wrapper">
      <div class="np-icons-holder" @click="selectView(selectPhone)">
        <img src="https://i.ibb.co/PzLbkMY/phone-2.png" />
      </div>
      <div class="np-icons-holder" @click="selectView(selectNotes)">
        <img src="https://i.ibb.co/PwhFXd2/notes.png" />
      </div>
      <div class="np-icons-holder" @click="selectView(selectGallery)">
        <img src="https://i.ibb.co/b2J7MtF/photos.png" />
      </div>
      <div class="np-icons-holder" @click="selectView(selectClock)">
        <img src="https://i.ibb.co/m0cg5wS/clock.png" />
      </div>
    </div>
  </div>
</template>

<script>
import PhoneView from "./PhoneView";
import NotesView from "./NotesView";
import GalleryView from "./GalleryView";
import ClockView from "./ClockView";
import HomeWidget from "./HomeWidget";

export default {
  name: "MainWrapper",
  components: {
    PhoneView,
    NotesView,
    GalleryView,
    ClockView,
    HomeWidget,
  },
  data() {
    return {
      selectedView: null,
      selectableViews: {
        home: -1,
        phone: 0,
        notes: 1,
        gallery: 2,
        clock: 3,
      },
      selectHome: -1,
      selectPhone: 0,
      selectNotes: 1,
      selectGallery: 2,
      selectClock: 3,
    };
  },
  methods: {
    selectView(viewToSelect) {
      if (this.selectedView === viewToSelect) {
        this.selectedView = this.selectHome;
      } else {
        this.selectedView = viewToSelect;
      }
    },
  },
};
</script>

<style>
.np-wrapper-container {
  position: relative;
  height: 500px;
  width: 250px;
  border: 1px solid #eee;
  background: url(https://i.ibb.co/pjPFT82/iphone-13-wallpaper.jpg);
}
.np-icons-wrapper {
  position: absolute;
  height: 54px;
  width: 240px;
  margin: 0 5px;
  background: rgba(238, 238, 238, 0.568);
  bottom: 0;
  border-radius: 6px;
  transform: translateY(-6px);
}
.np-icons-holder {
  display: inline-block;
  width: 24%;
  height: 50px;
  transform: translateY(3px) translateX(4px) scale(0.9);
  text-align: center;
  transition: all 0.3s;
  cursor: pointer;
}
.np-icons-holder:hover {
  transform: translateY(3px) scale(1);
  transition: all 0.3s;
}
</style>