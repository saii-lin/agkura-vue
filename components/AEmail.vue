<template>
  <div class="email">
    <div class="email_content max-width">
      <div class="email_text max-width">
        <p class="email_need">*&nbsp;&nbsp;為必填</p>
        <p class="email_title">若您希望我們與您聯絡，請在此留下聯絡信息，我們的專員會盡快與您接洽。</p>
      </div>
      <div class="form">
        <div class="form-body max-width">
          <div class="input">
            <input class="text" placeholder="名字*" type="text" name="fullName" value />
            <input class="text" placeholder="電子郵件*" type="text" name="email" value />
            <input class="text" placeholder="主旨" type="text" name="title" value />
          </div>
          <div>
            <textarea placeholder="訊息內容" name="message"></textarea>
          </div>
          <div>
            <input type="hidden" name="captchaToken" />
            <input type="hidden" name="locale" value="zh_TW" />
            <!-- en_US, zh_CN, zh_TW -->
            <input type="hidden" name="emailTo" value="info@agkuratec.com" />
          </div>
        </div>
        <div class="actions-grid">
          <div>
            <div>
              <div class="captcha-image" title="刷新"></div>
            </div>
            <div class="input">
              <input class="text" type="text" name="captchaInput" placeholder="請輸入驗證碼*" />
            </div>
            <div class="button_">
              <input class="button" type="submit" value="送出" />
            </div>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {};
var config = {
  API_origin:
    "http://infostrum-contact.azurewebsites.net/api/infostrum-contact",
  subjectPrefix: "Websites Enquiry - ",
  validation: {
    msg: {
      success: "發送成功",
      failed: "發送失敗(請檢查驗證碼)",
      required: "請輸入完整資料"
    }
  }
};

$(function() {
  initCaptcha();
  bindFormSubmit();
});

function bindFormSubmit() {
  document
    .querySelector(".form [type='submit']")
    .addEventListener("click", formSubmit);
}

function formSubmit() {
  var fullNameDOM = document.querySelector(".form [name='fullName']");
  var emailDOM = document.querySelector(".form [name='email']");
  var captchaInputDOM = document.querySelector(".form [name='captchaInput']");
  if (fullNameDOM.value && emailDOM.value && captchaInputDOM.value) {
    contact();
  } else {
    alert(config.validation.msg.required);
  }
}

function prepareContactBody() {
  var parameters = [
    { name: "fullName", required: true },
    { name: "email", required: true },
    { name: "message", required: true },
    { name: "captchaInput", required: true },
    { name: "captchaToken" },
    { name: "emailTo", required: true },
    { name: "locale" }
  ];
  var body = Object.create(null);
  for (var i = 0; i < parameters.length; i++) {
    var parameter = parameters[i];
    var dom = document.querySelector(".form [name='" + parameter.name + "']");
    if (parameter.required && !dom) {
      console.error(
        "parameter:" +
          parameter.name +
          "is not found, please check the selector: [name='" +
          parameter.name +
          "'] exists"
      );
    }
    if (dom) {
      body[parameters[i].name] = dom.value;
    }
  }

  var title = document.querySelector(".form [name='title']").value;
  body.subject = config.subjectPrefix + title;

  return body;
}

function contact() {
  $.ajax({
    type: "POST",
    url: config.API_origin,
    data: JSON.stringify(prepareContactBody()),
    dataType: "json",
    crossDomain: true,
    success: function(data) {
      if (data.success) {
        alert(config.validation.msg.success);
        clearAllInputs();
      } else {
        console.log(data.message);
        alert(config.validation.msg.failed);
        refreshCaptcha();
      }
    }
  });
}

function initCaptcha() {
  refreshCaptcha();
  document
    .querySelector(".captcha-image")
    .addEventListener("click", refreshCaptcha);
}

function refreshCaptcha() {
  var captchaTokenDOM = document.querySelector(".form [name='captchaToken']");
  var captchaImgDOM = document.querySelector(".form .captcha-image");
  var captchaInputDOM = document.querySelector(".form [name='captchaInput']");
  $.get(config.API_origin, function(data) {
    captchaTokenDOM.value = data.token;
    captchaImgDOM.innerHTML = data.svg;
    clearInput(captchaInputDOM);
  });
}

function clearAllInputs() {
  var inputs = ["fullName", "email", "title", "message", "captchaInput"];
  for (var i = 0; i < inputs.length; i++) {
    var inputDOM = document.querySelector(".form [name='" + inputs[i] + "']");
    if (inputDOM) {
      clearInput(inputDOM);
    }
  }
}

function clearInput(inputDOM) {
  inputDOM.value = "";
}
</script>

<style>
.max-width {
  max-width: 1280px;
  margin: 0 auto;
}
.email {
  background: #002f6c;
}

.email_title {
  color: #fff;
  margin: 0;
  text-align: center;
  font-size: 18px;
  letter-spacing: 1px;
}

.email_need {
  color: #fff;
  margin: 0;
  letter-spacing: 1px;
}

.form-body {
  display: flex;
  justify-content: center;
}

.input {
  display: flex;
  flex-direction: column;
}

.input .text {
  width: 355px;
  height: 30px;
  margin: 20px;
  background: transparent;
  border: 1px solid #fff;
  border-radius: 5px;
  color: rgb(151, 151, 151);
}

textarea {
  width: 60vw;
  height: 180px;
  margin: 20px 0 0 0;
  background: transparent;
  border: 1px solid #fff;
  border-radius: 5px;
  color: rgb(151, 151, 151);
}

.button {
  color: #002f6c;
  background: #baddf9;
  width: 80px;
  float: right;
  text-align: center;
  border-radius: 5px;
  font-size: 18px;
  padding: 5px;
  font-weight: bold;
  cursor: pointer;
}

.button.disabled {
  cursor: no-drop;
  color: #fff;
  background: #ccc;
}

.captcha-image {
  background: #ccc;
  border-radius: 10px;
}

.text1 {
  position: absolute;
  right: 25%;
  width: 100px;
  height: 24px;
  border-radius: 5px;
}

.capttcha {
  width: 120px;
  height: 24px;
}

.email_need {
  margin-left: 20px;
  letter-spacing: 1px;
  font-size: 18px;
}

.email_text {
  display: grid;
  grid-template-columns: 340px auto;
  padding-top: 20px;
  line-height: 30px;
  margin: auto;
}

.actions-grid {
  display: grid;
  justify-content: end;
}

.actions-grid > div {
  display: grid;
  grid-template-columns: 160px 160px 100px;
  grid-column: 10px;
  align-items: center;
}

.actions-grid .input .text {
  width: 100px;
  padding: 4px 8px;
}

.actions-grid .captcha-image {
  cursor: pointer;
}
</style>