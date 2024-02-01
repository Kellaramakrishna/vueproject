<template>
  <nav class="nav-header">
    <div class="nav-content">
      <p class="website-logo">RA</p>
      <ul class="nav-menu">
        <li>
          <img
            class="social-network-img"
            src="https://res.cloudinary.com/dpcgriaf4/image/upload/v1706760354/LinkedIn_logo_initials_uaqxh6.png"
            alt="Linked In"
          />
        </li>
        <li>
          <img
            class="social-network-img"
            src="https://res.cloudinary.com/dpcgriaf4/image/upload/v1706760476/25231_myoaj1.png"
            alt="Git Hub"
          />
        </li>
        <li>
          <img
            class="social-network-img"
            src="https://res.cloudinary.com/dmwrugc6z/image/upload/v1621681890/Background_4x_1_bzyjew.png"
            alt="Twitter"
          />
        </li>
      </ul>
    </div>
  </nav>
</template>

<script>
export default {
  name: "AppHeader",
};
</script>

<style scoped>
.nav-header {
  display: flex;
  justify-content: center;
  margin: auto;
  width: 90%;
  margin: auto;
  height: 60px;
  max-width: 1110px;
  box-shadow: 2px 2px 5px #d9d8d4;
  border-radius: 10px;
}

@media screen and (min-width: 992px) {
  .nav-header {
    width: 100%;
    height: 100px;
  }
}

.nav-content {
  flex: 1;
  display: flex;
  align-items: center;
  justify-content: space-between;
  padding-top: 25px;
  padding-bottom: 25px;
  padding: 10px;
}

.website-logo {
  font-size: 12px;
  margin-left: 20px;
  width: 30px;
  height: 30px;
  border-radius: 12px;
  text-align: center;
  font-weight: 900;
  color: #1d4ed8;
  display: flex;
  justify-content: center;
  align-items: center;
  background-color: #dbeafe;
}

@media screen and (min-width: 768px) {
  .website-logo {
    font-size: 23px;
    width: 40px;
    height: 40px;
  }
}

.nav-menu {
  display: flex;
  flex-direction: row;
  justify-content: flex-end;
  align-self: center;
  flex: 1;
  list-style-type: none;
  margin-top: 0;
  margin-bottom: 0;
}

.social-network-img {
  width: 30px;
  margin-left: 15px;
}

@media screen and (min-width: 768px) {
  .social-network-img {
    width: 35px;
    border-radius: 4px;
    margin-left: 32px;
  }
}
</style>
