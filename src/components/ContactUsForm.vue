<template>
  <div class="contactUsForm">
    <ModularForm
      title="Have us reach out"
      :fields="fields"
      :onSuccessfulSubmission="ContactUsFormSubmitted"
      url="https://dev-api-api.hiring-test.experientialpreview.com/api/lead/e44f8c09-ab50-440d-a4a6-c6f0d2a2cab0"
    />
  </div>
</template>

<script lang="ts">
import { defineComponent } from "vue";
import ModularForm from "./ModularForm.vue";

function ContactUsFormSubmitted() {
  console.log("here");
  window.location.href = "/thanks/";
}

export default defineComponent({
  name: "ContactUsForm",
  components: {
    ModularForm,
  },
  data() {
    return {
      ContactUsFormSubmitted,
      fields: [
        { title: "First Name", dataType: "text", id: "first" },
        { title: "Last Name", dataType: "text", id: "last" },
        { title: "Email", dataType: "email", id: "email" },
        { title: "Phone Number", dataType: "text", id: "phone" },
        { title: "Company", dataType: "text", id: "company" },
      ],
    };
  },
});
</script>
