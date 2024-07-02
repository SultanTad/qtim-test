<template>
  <footer class="footer">
    <div class="container">
      <div class="footer__inner">
        <div class="footer__contacts">
          <div class="footer__contacts-title">
            <p>Is there a project?</p>
            <h4>Let’s work</h4>
            <h4>together</h4>
          </div>
          <ul class="footer__contacts-data">
            <li>
              <dl>
                <dt>For all questions</dt>
                <dd><a href="tel:+79202780068">+7 (920) 278—00—68</a></dd>
                <dd><a href="mailto:qtim@agency.com">qtim@agency.com</a></dd>
              </dl>
            </li>
            <li>
              <dl>
                <dt>Office in Russia</dt>
                <dd>139 Ruben Station Lake Drew, NM 52678</dd>
                <dd>
                  <img src="../assets/images/buttonlocation.png" alt="" />
                </dd>
              </dl>
            </li>
            <li>
              <dl>
                <dt>Office in Dubai</dt>
                <dd>139 Ruben Station Lake Drew, NM 52678</dd>
                <dd>
                  <img src="../assets/images/buttonlocation.png" alt="" />
                </dd>
              </dl>
            </li>
          </ul>
        </div>
        <div class="footer__links">
          <ul class="footer__links-list">
            <li class="footer__links-item">Facebook</li>
            <li class="footer__links-item">Instagram</li>
            <li class="footer__links-item">Telegram</li>
          </ul>
          <div class="footer__links-center">
            <h4>Go</h4>
          </div>
          <ul class="footer__links-list">
            <li class="footer__links-item">Behance</li>
            <li class="footer__links-item">Linkedn</li>
            <li class="footer__links-item">Privacy Policy</li>
          </ul>
        </div>
      </div>
    </div>
  </footer>
</template>

<style>
.footer {
  margin-top: 140px;
  overflow: hidden;
  background-color: #e2beff;
  font-family: "TTCommons-Regular";
  font-weight: 400;
  color: #000;
}

.footer__inner {
  padding-top: 140px;
  position: relative;
  height: 900px;
}

.footer__contacts {
  display: flex;
  justify-content: space-between;
}

.footer__contacts-title p {
  margin-bottom: 56px;
}

.footer__contacts-title h4 {
  font-size: 112px;
  line-height: 112px;
  font-weight: 400;
  max-width: 464px;
  position: relative;
}

.footer__contacts-title h4::before {
  content: "";
  height: 1px;
  width: 100%;
  background-color: #000;
  position: absolute;
  left: 0;
  bottom: 16px;
}

.footer__contacts-data {
  max-width: 152px;
  display: flex;
  flex-direction: column;
  gap: 36px 0;
}

.footer__contacts-data li {
  font-size: 16px;
}

.footer__contacts-data li dl dt {
  margin-bottom: 12px;
}

.footer__contacts-data li dl dd {
  margin-bottom: 8px;
}

.footer__contacts-data li dl a {
  color: #000;
}

.footer__links {
  display: flex;
  align-items: center;
  justify-content: space-between;
  position: absolute;
  bottom: 0;
  padding-bottom: 30px;
  width: 100%;
}

.footer__links-list {
  display: flex;
  align-items: center;
  gap: 0 32px;
}

.footer__links-item {
  position: relative;
}

.footer__links-item::before {
  content: "";
  height: 0.4px;
  width: 100%;
  background-color: #000;
  position: absolute;
  left: 0;
  bottom: 0;
}

.footer__links-center {
  height: 358px;
  width: 358px;
  background-color: #000;
  color: #fff;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 100%;
  position: absolute;
  right: 35%;
}

.footer__links-center h4 {
  font-family: "TTCommons-Regular";
  font-size: 32px;
  line-height: 32px;
  font-weight: 400;
}
</style>
