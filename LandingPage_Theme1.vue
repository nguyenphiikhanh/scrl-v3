<script setup lang="ts">
import { onMounted, onUnmounted, ref } from "@vue/runtime-core";
import { useRouter } from "vue-router";
import { getAgencyName } from "@/base/functions/commonFns";
import { onBeforeMount } from "vue";
import { LocalStorageKey } from "@/commons/constants/localstorage-key";
import { getLocalStorage } from "@/base/functions/localStorageFns";
import { ThemeColor, ThemeNameDefault } from "@/commons/constants/theme-config";

const headerRef = ref<any>(null);
const landingPage = ref<any>(null);
const fullPageGreen = ref<any>(null);
const checkboxVal = ref(false);
const overView = ref();
const serviceProvided = ref();
const priceList = ref();
const contactPage = ref();
const position = ref<any>([]);
const activeClass = ref(1);
const agencyName = ref("");

const router = useRouter();

const toggleMenu = () => {
  checkboxVal.value = !checkboxVal.value;
};

onBeforeMount(() => {
  // Kiểm tra đã có token chưa - nếu chưa thì điều hướng ra login
  const themeName =
    getLocalStorage(LocalStorageKey.AutoLike_Theme) || ThemeNameDefault;
  // Màu sắc theme
  const currentTheme = ThemeColor.find((item) => item.ThemeName == themeName);
  // Danh sách class của theme
  const colorClass = currentTheme?.ColorClass || [
    "light-style",
    "dark-style",
    "carmine-style",
    "darkmoon-style",
  ];
  // Remove class
  colorClass.forEach((cl: string) => {
    document.body.classList.remove(cl);
  });
});

onMounted(() => {
  position.value = [
    {
      height: overView.value.offsetHeight,
      top: overView.value.offsetTop,
    },
    {
      height: serviceProvided.value.offsetHeight,
      top: serviceProvided.value.offsetTop,
    },
    {
      height: priceList.value.offsetHeight,
      top: priceList.value.offsetTop,
    },
    {
      height: contactPage.value.offsetHeight,
      top: contactPage.value.offsetTop,
    },
  ];
  agencyName.value = getAgencyName();

  landingPage.value.addEventListener(
    "scroll",
    () => {
      if (landingPage.value.scrollTop != 0) {
        headerRef.value.classList.add("ative-header");
      } else {
        headerRef.value.classList.remove("ative-header");
      }
      handleScroll();
    },
    true
  );
  fullPageGreen.value.addEventListener("click", () => {
    toggleMenu();
  });
});
onUnmounted(() => {
  landingPage.value ? landingPage.value.removeEventListener("scroll") : "";
});

const scrollIntoView = (key: any) => {
  checkboxVal.value = false;
  switch (key) {
    case 1:
      overView.value.scrollIntoView({
        behavior: "smooth",
      });
      break;
    case 2:
      serviceProvided.value.scrollIntoView({
        behavior: "smooth",
      });
      break;
    case 3:
      priceList.value.scrollIntoView({
        behavior: "smooth",
      });
      break;
    case 4:
      contactPage.value.scrollIntoView({
        behavior: "smooth",
      });
      break;

    default:
      overView.value.scrollIntoView({
        behavior: "smooth",
      });
      break;
  }
  setTimeout(() => {
    activeClass.value = key;
  }, 800);
};

const handleScroll = () => {
  position.value = [
    Math.floor(overView.value.offsetHeight),
    Math.floor(serviceProvided.value.offsetHeight) + position.value[0],
    Math.floor(priceList.value.offsetHeight) + position.value[1],
    Math.floor(contactPage.value.offsetHeight) + position.value[2],
  ];
  if (
    position.value[0] - landingPage.value.scrollTop > 0 &&
    landingPage.value.scrollTop > overView.value.offsetTop
  ) {
    activeClass.value = 1;
  }
  if (
    position.value[1] - landingPage.value.scrollTop > 0 &&
    landingPage.value.scrollTop > serviceProvided.value.offsetTop
  ) {
    activeClass.value = 2;
  }
  if (
    position.value[2] - landingPage.value.scrollTop > 0 &&
    landingPage.value.scrollTop > priceList.value.offsetTop
  ) {
    activeClass.value = 3;
  }
  if (
    position.value[3] - landingPage.value.scrollTop > 0 &&
    landingPage.value.scrollTop > contactPage.value.offsetTop
  ) {
    activeClass.value = 4;
  }
};
const redirectLogin = () => {
  router.push("/login");
};
</script>

<template>
  <div id="landing-page-theme1" class="font-roboto" ref="landingPage">
    <div class="header-landing-page" ref="headerRef">
      <header>
        <div class="logo">
          <template v-if="agencyName">
            <svg
              class="logo-2"
              xmlns="http://www.w3.org/2000/svg"
              width="50"
              height="30"
              viewBox="0 0 50 30"
              fill="#4E89FF"
            >
              <g clip-path="url(#clip0)">
                <path
                  d="M19.9195 17.7344C19.7755 17.7344 19.622 17.7056 19.478 17.6479L0.765061 10.2849C0.314031 10.1022 0.0069466 9.66968 0.0069466 9.17945C-0.00264978 8.68922 0.285242 8.24706 0.736272 8.05481L19.4492 0.0862126C19.7467 -0.0387473 20.0922 -0.0387473 20.3897 0.0862126L39.1026 8.05481C39.5537 8.24706 39.8415 8.68922 39.8319 9.17945C39.8224 9.66968 39.5249 10.1022 39.0738 10.2849L20.3609 17.6479C20.2169 17.7056 20.0634 17.7344 19.9195 17.7344ZM4.3733 9.13139L19.9195 15.2448L35.4656 9.13139L19.9195 2.50851L4.3733 9.13139Z"
                ></path>
                <path
                  d="M19.9096 23.8673C19.7656 23.8673 19.6121 23.8385 19.4682 23.7808L0.755203 16.4178C0.141034 16.1871 -0.156454 15.4854 0.083456 14.8702C0.323366 14.255 1.0239 13.9474 1.63807 14.1877L19.9096 21.3778L38.1811 14.1877C38.7953 13.9474 39.4958 14.2454 39.7357 14.8702C39.9756 15.4854 39.6782 16.1871 39.0544 16.4274L20.3414 23.7904C20.2071 23.8385 20.0631 23.8673 19.9096 23.8673Z"
                ></path>
                <path
                  d="M19.9096 30C19.7656 30 19.6121 29.9712 19.4681 29.9135L0.755181 22.5505C0.141012 22.3102 -0.166072 21.6085 0.0738377 20.9933C0.313747 20.3781 1.01428 20.0705 1.62845 20.3108L19.9 27.5008L38.1715 20.3108C38.7857 20.0705 39.4862 20.3685 39.7261 20.9933C39.966 21.6085 39.6685 22.3102 39.0448 22.5505L20.3318 29.9135C20.2071 29.9712 20.0631 30 19.9096 30Z"
                ></path>
              </g>
              <defs>
                <clipPath id="clip0">
                  <rect width="50" height="30" fill="white"></rect>
                </clipPath>
              </defs>
            </svg>
            <span class="font-logo position-absolute">{{ agencyName }}</span>
          </template>
          <img
            v-else
            src="/assets/images/theme1/logo.svg"
            class="logo-landing-page"
          />
        </div>
        <div class="menu">
          <div
            class="item-menu"
            :class="activeClass == 1 ? 'active-menu' : ''"
            @click="scrollIntoView(1)"
          >
            Trang chủ
          </div>
          <div
            class="item-menu"
            :class="activeClass == 2 ? 'active-menu' : ''"
            @click="scrollIntoView(2)"
          >
            Dịch vụ
          </div>
          <div
            class="item-menu"
            :class="activeClass == 3 ? 'active-menu' : ''"
            @click="scrollIntoView(3)"
          >
            Bảng giá
          </div>
          <div
            class="item-menu"
            :class="activeClass == 4 ? 'active-menu' : ''"
            @click="scrollIntoView(4)"
          >
            Liên Hệ
          </div>
        </div>
        <div class="btn-login btn-header">
          <button @click="redirectLogin">Đăng nhập</button>
          <label for="ham-menu">
            <p></p>
          </label>
        </div>
      </header>
    </div>
    <div class="over-view" ref="overView" id="1">
      <div class="over-view-body">
        <div class="content-text">
          <h1>Tương tác với bạn bè hiệu quả hơn với {{ agencyName }}</h1>
          <p>
            {{ agencyName }} chuyên cung cấp các dịch vụ tăng Like, Share,
            Comment, Follow... cho các Mạng xã hội như Facebook, Instagram,
            Tikok
          </p>
          <div class="btn-login-over-view btn-login">
            <button @click="redirectLogin">Đăng nhập</button>
          </div>
        </div>
        <div class="phone-image">
          <!-- <p class="phone-image-backgr"></p> -->
          <img src="/assets/images/theme1/phone.png" alt="" />
        </div>
      </div>
    </div>
    <div class="service-provided" ref="serviceProvided" id="2">
      <div class="autolike-service-title">
        <p>{{ agencyName }} services</p>
        <h2>Dịch vụ cung cấp</h2>
      </div>
      <div class="service-name">
        <div class="facebook">
          <img
            class="image-service-name"
            src="/assets/images/theme1/facebook.svg"
          />
        </div>
        <div class="instagram">
          <img
            class="image-service-name"
            src="/assets/images/theme1/instagramWhite.svg"
          />
        </div>
        <div class="tiktok">
          <img
            class="image-service-name"
            src="/assets/images/theme1/tiktokWhite.svg"
          />
        </div>
      </div>
      <div class="outstanding-features">
        <div class="features-top">
          <div class="image-features">
            <img src="/assets/images/theme1/people.svg" />
          </div>
          <div class="text-features">
            <h2>Đặc điểm nổi bật của {{ agencyName }}</h2>
            <ul>
              <li>
                <button class="dot">•</button>
                <span>Dịch vụ được thực hiện bởi 100% là người Việt Nam</span>
              </li>
              <li>
                <button class="dot">•</button>
                <span>Tài khoản đang sử dụng MXH, Like thật, view thật,…</span>
              </li>
              <li>
                <button class="dot">•</button>
                <span
                  >Mua số lượng lớn sẽ có hợp đồng mua bán đúng pháp luật</span
                >
              </li>
              <li>
                <button class="dot">•</button>
                <span>Cam kết chất lượng và giá tốt nhất trên thị trường</span>
              </li>
            </ul>
          </div>
        </div>
        <div class="features-bottom">
          <ul>
            <li>
              <button class="dot">•</button>
              <span
                >Tăng Like Facebook giúp thể hiện sự quan tâm, đánh giá cao nội
                dung (Như ý nghĩa vốn có). Đồng nghĩ với việc bài viết của bạn
                sẽ được nhiều sự quan tâm hơn khi có nhiều Like hơn và việc
                maketing mọi thứ sẽ trở nên hiệu quả hơn!</span
              >
            </li>
            <li>
              <button class="dot">•</button>
              <span
                >Đối với doanh nghiệp, Like Page thể hiện số lượng khán giả quan
                tâm đến thương hiệu, hay khách hàng tiềm năng. Nó cũng quyết
                định mỗi nội dung mới bạn đăng sẽ tiếp cận được bao nhiêu khách
                hàng tiềm năng. Ngoài ra, lượt like page cũng phần nào đại diện
                cho mức độ UY TÍN. Càng có nhiều lượt like Page, thương hiệu
                càng được đánh giá cao. Nó là yếu tố cực kì quan trọng, đặc biệt
                là ở giai đoạn chốt đơn hàng.</span
              >
            </li>
            <li>
              <button class="dot">•</button>
              <span
                >Một trong những lợi ích lớn nhất mang lại của Facebook comment
                là tăng khả năng bao phủ của bạn trên mạng xã hội Facebook. Điều
                này giúp bạn tăng tương tác trên mạng xã hội, giúp mọi hoạt động
                của bạn được chú ý hơn!
              </span>
            </li>
          </ul>
        </div>
      </div>
      <div class="description-features"></div>
    </div>
    <div class="price-list" ref="priceList" id="3">
      <div class="price-list-title">
        <p>Price list</p>
        <h2>Bảng giá dịch vụ</h2>
      </div>
      <div class="service-block">
        <div class="instagram-block left-block">
          <div class="logo">
            <img src="/assets/images/theme1/instagram.svg" />
          </div>
          <div class="detailt-service close">
            <div class="text-service">
              <div class="name">
                <span>
                  <div class="tick-mark"><p></p></div>
                  <div class="text-service-elm">Tăng Like bài viết</div>
                </span>
                <div class="in-name">
                  <span><strong>27đ</strong>/lượt</span>
                </div>
                <div class="des">
                  <span class="text-des">Max 100,000 lượt</span>
                </div>
              </div>
            </div>
            <div class="price-serice">
              <span><strong>27đ</strong>/lượt</span>
            </div>
          </div>
          <div class="detailt-service close">
            <div class="text-service">
              <div class="name">
                <span>
                  <div class="tick-mark"><p></p></div>
                  <div class="text-service-elm">Tăng theo dõi tài khoản</div>
                </span>
                <div class="in-name">
                  <span><strong>27đ</strong>/lượt</span>
                </div>
                <div class="des">
                  <span class="text-des">Max 100,000 lượt</span>
                </div>
              </div>
            </div>
            <div class="price-serice">
              <span><strong>27đ</strong>/lượt</span>
            </div>
          </div>
        </div>
        <div class="facebook-block center-block">
          <div class="logo">
            <img src="/assets/images/theme1/facebookWhite.svg" />
          </div>
          <div class="detailt-service open">
            <div class="text-service">
              <div class="name">
                <span>
                  <div class="tick-mark"><p></p></div>
                  Gói Sub/Follow
                </span>
                <div class="in-name">
                  <span><strong>17đ</strong>/lượt</span>
                </div>
                <div class="des">
                  <span>Max 200,000 lượt</span>
                </div>
              </div>
            </div>
            <div class="price-serice">
              <span><strong>17đ</strong>/lượt</span>
            </div>
          </div>
          <div class="detailt-service open">
            <div class="text-service">
              <div class="name">
                <span>
                  <div class="tick-mark"><p></p></div>
                  Gói Like Fanpage
                </span>
                <div class="in-name">
                  <span><strong>17đ</strong>/lượt</span>
                </div>
                <div class="des">
                  <span>Max 200,000 lượt</span>
                </div>
              </div>
            </div>
            <div class="price-serice">
              <span><strong>17đ</strong>/lượt</span>
            </div>
          </div>
          <div class="detailt-service open">
            <div class="text-service">
              <div class="name">
                <span>
                  <div class="tick-mark"><p></p></div>
                  Gói Buff Like
                </span>
                <div class="in-name">
                  <span><strong>4đ</strong>/lượt</span>
                </div>
                <div class="des">
                  <span>Max 100,000 lượt</span>
                </div>
              </div>
            </div>
            <div class="price-serice">
              <span><strong>4đ</strong>/lượt</span>
            </div>
          </div>
          <div class="detailt-service open">
            <div class="text-service">
              <div class="name">
                <span>
                  <div class="tick-mark"><p></p></div>
                  Gói Buff Comment
                </span>
                <div class="in-name">
                  <span><strong>38đ</strong>/lượt</span>
                </div>
                <div class="des">
                  <span>Max 100,000 lượt</span>
                </div>
              </div>
            </div>
            <div class="price-serice">
              <span><strong>38đ</strong>/lượt</span>
            </div>
          </div>
          <div class="detailt-service open">
            <div class="text-service">
              <div class="name">
                <span>
                  <div class="tick-mark"><p></p></div>
                  Gói VIP Like
                </span>
                <div class="in-name">
                  <span><strong>1,000đ</strong>/lượt</span>
                </div>
                <div class="des">
                  <span>Max 10,000 lượt</span>
                </div>
              </div>
            </div>
            <div class="price-serice">
              <span><strong>1,000đ</strong>/lượt</span>
            </div>
          </div>
          <div class="detailt-service close">
            <div class="text-service">
              <div class="name">
                <span>
                  <div class="tick-mark"><p></p></div>
                  Gói VIP Comment
                </span>
                <div class="in-name">
                  <span><strong>0đ</strong>/lượt</span>
                </div>
                <div class="des">
                  <span>Max 0 lượt</span>
                </div>
              </div>
            </div>
            <div class="price-serice">
              <span><strong>0đ</strong>/lượt</span>
            </div>
          </div>
        </div>
        <div class="tiktok-block right-block">
          <div class="logo">
            <img src="/assets/images/theme1/tiktok.svg" />
          </div>
          <div class="detailt-service close">
            <div class="text-service">
              <div class="name">
                <span>
                  <div class="tick-mark"><p></p></div>
                  <div class="text-service-elm">Tăng Like/ tim bài viết</div>
                </span>
                <div class="in-name">
                  <span><strong>27đ</strong>/lượt</span>
                </div>
                <div class="des">
                  <span class="text-des">Max 100,000 lượt</span>
                </div>
              </div>
            </div>
            <div class="price-serice">
              <span><strong>27đ</strong>/lượt</span>
            </div>
          </div>
          <div class="detailt-service close">
            <div class="text-service">
              <div class="name">
                <span>
                  <div class="tick-mark"><p></p></div>
                  <div class="text-service-elm">Tăng theo dõi cá nhân</div>
                </span>
                <div class="in-name">
                  <span><strong>27đ</strong>/lượt</span>
                </div>
                <div class="des">
                  <span class="text-des">Max 100,000 lượt</span>
                </div>
              </div>
            </div>
            <div class="price-serice">
              <span><strong>27đ</strong>/lượt</span>
            </div>
          </div>
        </div>
      </div>
    </div>
    <div class="contact-page" ref="contactPage" id="4">
      <div class="contact-page-body">
        <div class="contact">
          <h2>Liên hệ với chúng tôi</h2>
          <div class="contact-facebook">
            <p>Fanpage hỗ trợ</p>
            <p>
              <a href="www.facebook.com/autolikecc"
                >www.facebook.com/autolikecc</a
              >
            </p>
          </div>
          <div class="contact-facebook">
            <p>Hotline</p>
            <p>+84 39 438 6880</p>
          </div>
          <div class="contact-logo">
            <template v-if="agencyName">
              <div class="my-1">
                <svg
                  class="logo-2"
                  xmlns="http://www.w3.org/2000/svg"
                  width="50"
                  height="30"
                  viewBox="0 0 50 30"
                  fill="#fff"
                >
                  <g clip-path="url(#clip0)">
                    <path
                      d="M19.9195 17.7344C19.7755 17.7344 19.622 17.7056 19.478 17.6479L0.765061 10.2849C0.314031 10.1022 0.0069466 9.66968 0.0069466 9.17945C-0.00264978 8.68922 0.285242 8.24706 0.736272 8.05481L19.4492 0.0862126C19.7467 -0.0387473 20.0922 -0.0387473 20.3897 0.0862126L39.1026 8.05481C39.5537 8.24706 39.8415 8.68922 39.8319 9.17945C39.8224 9.66968 39.5249 10.1022 39.0738 10.2849L20.3609 17.6479C20.2169 17.7056 20.0634 17.7344 19.9195 17.7344ZM4.3733 9.13139L19.9195 15.2448L35.4656 9.13139L19.9195 2.50851L4.3733 9.13139Z"
                    ></path>
                    <path
                      d="M19.9096 23.8673C19.7656 23.8673 19.6121 23.8385 19.4682 23.7808L0.755203 16.4178C0.141034 16.1871 -0.156454 15.4854 0.083456 14.8702C0.323366 14.255 1.0239 13.9474 1.63807 14.1877L19.9096 21.3778L38.1811 14.1877C38.7953 13.9474 39.4958 14.2454 39.7357 14.8702C39.9756 15.4854 39.6782 16.1871 39.0544 16.4274L20.3414 23.7904C20.2071 23.8385 20.0631 23.8673 19.9096 23.8673Z"
                    ></path>
                    <path
                      d="M19.9096 30C19.7656 30 19.6121 29.9712 19.4681 29.9135L0.755181 22.5505C0.141012 22.3102 -0.166072 21.6085 0.0738377 20.9933C0.313747 20.3781 1.01428 20.0705 1.62845 20.3108L19.9 27.5008L38.1715 20.3108C38.7857 20.0705 39.4862 20.3685 39.7261 20.9933C39.966 21.6085 39.6685 22.3102 39.0448 22.5505L20.3318 29.9135C20.2071 29.9712 20.0631 30 19.9096 30Z"
                    ></path>
                  </g>
                  <defs>
                    <clipPath id="clip0">
                      <rect width="50" height="30" fill="white"></rect>
                    </clipPath>
                  </defs>
                </svg>
                <span
                  class="font-logo position-absolute"
                  style="color: #fff; opacity: 1"
                  >{{ agencyName }}</span
                >
              </div>
              <br />
            </template>
            <p v-else></p>
            <span>Copyright by 2020 {{ agencyName }}</span>
          </div>
        </div>
        <div class="message">
          <h2>Gửi tin nhắn</h2>
          <p>Liên hệ với chúng tôi để được hỗ trợ nhanh nhất</p>
          <input
            type="text"
            placeholder="Số điện thoại đăng ký"
            class="cus-input"
          />
          <textarea
            name="content"
            id="content"
            placeholder="Nhập tin nhắn"
            rows="8"
            class="cus-input"
          ></textarea>
          <div class="submit">
            <button>Gửi tin nhắn</button>
          </div>
        </div>
      </div>
    </div>

    <!-- Menu side -->
    <input type="checkbox" id="ham-menu" v-model="checkboxVal" />
    <div class="full-page-green" ref="fullPageGreen"></div>
    <div class="ham-menu">
      <div class="label-ham-menu">
        <label for="ham-menu" class="icon-close">✕</label>
      </div>
      <ul class="centre-text bold-text">
        <li
          class="item-menu"
          :class="activeClass == 1 ? 'active-menu' : ''"
          @click="scrollIntoView(1)"
        >
          Trang chủ
        </li>
        <li
          class="item-menu"
          :class="activeClass == 2 ? 'active-menu' : ''"
          @click="scrollIntoView(2)"
        >
          Dịch vụ
        </li>
        <li
          class="item-menu"
          :class="activeClass == 3 ? 'active-menu' : ''"
          @click="scrollIntoView(3)"
        >
          Bảng giá
        </li>
        <li
          class="item-menu"
          :class="activeClass == 4 ? 'active-menu' : ''"
          @click="scrollIntoView(4)"
        >
          Liên Hệ
        </li>
      </ul>
    </div>
  </div>
</template>
<style src="@/assets/themes/theme1/scss/styleLandingPageTheme1.scss" scoped>
.logo-2 {
  fill: var(--color-active-sidebar);
}
</style>
