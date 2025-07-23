<template>
  <form>
    <div style="left: 36px; top: 208px; position: absolute">
      <h1
        style="width: 310px; height: 29px; position: absolute"
        class="contactFormTitle"
      >
        {{ props.title }}
      </h1>
      <div style="top: 74.95px; margin: 0; padding: 0; position: absolute">
        <div
          class="contactFormLabelContainer"
          v-for="ref in refs"
          :key="ref.value.id"
        >
          <span class="contactFormLabel">
            {{ ref.value.title }}
          </span>
          <div class="contactFormRectangle">
            <input
              class="contactFormInput"
              type="{{ field.dataType }}"
              v-model="ref.value.value"
            />
          </div>
        </div>
        <div
          style="
            position: relative;
            min-width: 310px;
            min-height: 30px;
            top: 20.65px;
          "
        >
          <input
            @click="handleSubmission()"
            type="button"
            value="Continue"
            class="contactFormSubmitBtn"
          />
        </div>
      </div>
    </div>
  </form>
</template>

<script setup lang="ts">
import { defineProps } from "vue";
import axios from "axios";
import { ref } from "vue";

/** @description an input field */
interface field {
  /** @description the title that should be displayed to the user for this field */
  title: string;
  /** @description the <input type=""> */
  dataType: string;
  /** @description the id that should be used for sending data to the url upon submission */
  id: string;
}

interface Props {
  /** @description the title of this form */
  title: string;
  /** @description an array of fields to render for this form */
  fields: field[];
  /**
   * @description the url endpoint to submit the data to
   */
  url: string;
  /**
   * @description called after a successful submission to the url
   */
  onSuccessfulSubmission: () => void;
}

const props = defineProps<Props>();
let refs = [];
props.fields.forEach((field) => {
  refs.push(
    ref({
      title: field.title,
      id: field.id,
      value: "",
    })
  );
});

async function handleSubmission() {
  try {
    let data = {};
    let valid = true;
    let err = "";

    //add all our form values to an object formatted how the api wants while checking if they are all atleast partially filled
    refs.forEach((ref) => {
      data[ref.value.id] = ref.value.value;
      if (ref.value.value.length == 0) {
        valid = false;
        err = "Please fill out all fields before submitting.";
      }
      if (ref.value.id == "email" && valid) {
        valid = valid
          ? /^\w+([.-]?\w+)*@\w+([.-]?\w+)*(.\w{2,3})+$/.test(ref.value.value)
          : false;

        err = valid ? "" : "Please use a valid email address.";
      }
      if (ref.value.id == "phone" && valid) {
        valid = /^\+?[1-9][0-9]{7,14}$/.test(ref.value.value);
        err = valid ? "" : "Please use a valid phone number.";
      }
    });

    //validate email and phone with regex

    if (valid) {
      const res = await axios.post(props.url, data);
    } else {
      window.alert(err);
      return;
    }
  } catch (err) {
    window.alert(`Bad Request. ${err}`);
    return;
  }
  props.onSuccessfulSubmission();
}
</script>

<script lang="ts">
import { defineComponent } from "vue";

export default defineComponent({
  name: "ModularForm",
});
</script>
