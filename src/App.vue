<template>
  <router-view />
</template>

<style lang="scss">
html,
body,
#app {
  min-height: 100dvh;
  background-color: #f4f2ee;
}

.contactFormInput {
  outline: none;
  border: none;
  background-color: transparent;
  width: 77;
  height: 18;
  opacity: 1;
  position: absolute;
  top: 12.66px;
  left: 20.1px;
  font-family: ABeeZee;
  font-weight: 400;
  font-style: Regular;
  font-size: 15px;
  leading-trim: NONE;
  line-height: 100%;
  letter-spacing: 0%;
}

.contactFormLabelContainer {
  background-color: #f4f2ee;
  padding-bottom: 71.28px;
  padding-left: 0;
  z-index: 0;
  position: relative;
}

.contactFormRectangle {
  border: 0.72px solid #555552;
  min-width: 310px;
  min-height: 40.31999969482422px;
  opacity: 1;
  border-radius: 3.6px;
  border-width: 0.72px;
  z-index: 0;
  position: absolute;
  display: block;
}

.contactFormSubmitBtn {
  min-width: 131px;
  min-height: 34.82982635498047px;
  opacity: 1;
  top: 0;
  right: 0;
  position: absolute;
  padding-top: 10.22px;
  padding-right: 37.5px;
  padding-bottom: 8.61px;
  padding-left: 37.5px;
  gap: 5.38px;
  border-radius: 4px;
  background-color: #0b476c;
  font-family: ABeeZee;
  font-weight: 400;
  font-style: Regular;
  font-size: 13.45px;
  line-height: 16px;
  letter-spacing: 0%;
  color: white;
}

ul li {
  display: absolute;
  padding: 0.4rem;
  text-align: left;
  left: 0;
}

.contactFormLabel {
  background-color: #f4f2ee;
  white-space: nowrap;
  font-family: ABeeZee;
  font-weight: 400;
  font-style: Regular;
  font-size: 12px;
  leading-trim: NONE;
  line-height: 100%;
  letter-spacing: 0%;
  padding-top: 1.26px;
  padding-right: 6.32px;
  padding-left: 6.32px;
  gap: 6.32px;
  color: #006315;
  position: absolute;
  z-index: 1;
  top: -5px;
  left: 13.07px;
}

.thankYouText {
  width: 227;
  height: 116;
  opacity: 1;
  top: 366px;
  left: 83px;
  font-family: Roboto;
  font-weight: 400;
  font-style: Regular;
  font-size: 25px;
  leading-trim: NONE;
  line-height: 100%;
  letter-spacing: 0%;
  text-align: center;
  position: absolute;
  color: #555552;
}

.contactFormTitle {
  color: #555552;
  padding-bottom: 54.95px;
  font-family: Roboto;
  font-weight: 400;
  font-style: Regular;
  font-size: 25px;
  leading-trim: NONE;
  line-height: 100%;
  letter-spacing: 0%;
}

.fade-enter-active,
.fade-leave-active {
  transition: opacity 0.25s;
}

.fade-enter-from,
.fade-leave-to {
  opacity: 0;
}
</style>
