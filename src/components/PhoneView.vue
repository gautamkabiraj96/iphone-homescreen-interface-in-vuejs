<template>
  <div class="np-app-container">
    <div class="np-app-title">Contacts</div>
    <div style="padding-top: 10px">
      <div v-for="(contact, c) in contacts" :key="c">
        <div class="np-contact-name" @mouseover="showContactInfo(contact)">
          {{ contact.name }}
        </div>
      </div>
      <div v-if="contactInfo" class="np-contact-info">
        <div class="no-contact-info--name">
          {{ contactInfo.name }}
        </div>
        <div class="np-contact-info--number">
          {{ contactInfo.number }}
        </div>
        <div class="np-contact-info--email">
          {{ contactInfo.email }}
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import { contactsList } from "./../data/contacts";

export default {
  name: "PhoneView",
  data() {
    return {
      contactInfo: null,
    };
  },
  computed: {
    contacts() {
      return contactsList;
    },
  },
  methods: {
    showContactInfo(contact) {
      this.contactInfo = contact;
    },
  },
};
</script>

<style>
.np-contact-name {
  font-size: 12px;
  border-bottom: 1px solid #e9e9e9;
  padding: 4px 0px;
  font-weight: normal;
  transition: all 0.3s;
  cursor: pointer;
}
.np-contact-name:hover {
  font-size: 12px;
  font-weight: bold;
  padding: 4px 0px;
  transition: all 0.3s;
  color: #0059ff;
}
.np-contact-info {
  font-size: 13px;
  border: 1px solid #e9e9e9;
  border-radius: 8px;
  margin-top: 10px;
  padding: 4px 10px;
}
.no-contact-info--name {
  font-size: 15px;
  padding-bottom: 4px;
}
.np-contact-info--email {
  color: #0059ff;
}
</style>