<template>
  <div class="nk-app-root" ref="landingPage" id="landing-page-2">
    <div class="nk-main">
      <header class="header has-header-main-s1 bg-lighter" id="home">
        <div class="header-main header-main-s1 is-sticky" ref="headerRef">
          <div class="container header-container">
            <div class="header-wrap">
              <div class="header-logo">
                <template v-if="agencyName">
                  <a href="/" class="logo-link">
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
                    <span class="font-logo position-absolute">{{
                      agencyName
                    }}</span>
                  </a>
                </template>
                <a href="/" class="logo-link" v-else>
                  <img
                    class="logo-light logo-img"
                    src="/assets/images/theme2/logo.svg"
                    alt="logo"
                  />
                  <img
                    class="logo-dark logo-img"
                    src="/assets/images/theme2/logo.svg"
                    alt="logo-dark"
                  />
                </a>
              </div>
              <div class="header-toggle">
                <button
                  class="menu-toggler"
                  ref="mobileMenuBtn"
                  data-target="mainNav"
                >
                  <em class="menu-on icon ni ni-menu"></em
                  ><em class="menu-off icon ni ni-cross"></em>
                </button>
              </div>
              <nav class="header-menu" data-content="mainNav">
                <ul class="menu-list mx-auto bg-white">
                  <li
                    class="menu-item pointer"
                    :class="activeClass == 1 ? 'active' : ''"
                    @click.prevent="scrollIntoView(1)"
                  >
                    <a class="menu-link nav-link">Trang chủ</a>
                  </li>
                  <li
                    class="menu-item pointer"
                    :class="activeClass == 2 ? 'active' : ''"
                    @click.prevent="scrollIntoView(2)"
                  >
                    <a class="menu-link nav-link">Dịch vụ</a>
                  </li>
                  <li
                    class="menu-item pointer"
                    :class="activeClass == 3 ? 'active' : ''"
                    @click.prevent="scrollIntoView(3)"
                  >
                    <a class="menu-link nav-link">Tính năng</a>
                  </li>
                  <li
                    class="menu-item pointer"
                    :class="activeClass == 4 ? 'active' : ''"
                    @click.prevent="scrollIntoView(4)"
                  >
                    <a class="menu-link nav-link">Bảng giá</a>
                  </li>
                  <li
                    class="menu-item pointer"
                    :class="activeClass == 5 ? 'active' : ''"
                    @click.prevent="scrollIntoView(5)"
                  >
                    <a class="menu-link nav-link">Đánh giá</a>
                  </li>
                </ul>
                <ul class="menu-btns d-flex bg-white">
                  <li>
                    <a
                      @click="onClickLogin"
                      class="btn btn-primary btn-lg text-white"
                      >Đăng nhập</a
                    >
                  </li>
                </ul>
              </nav>
            </div>
          </div>
        </div>
        <div class="header-content my-auto py-5 mt-n1" ref="overView">
          <div class="container">
            <div
              class="row flex-lg-row-reverse align-items-center justify-content-between g-gs"
            >
              <div class="col-lg-6 mb-n3 mb-lg-0">
                <div class="header-image header-image-s2">
                  <img src="/assets/images/theme2/banner1.png" alt />
                </div>
              </div>
              <div class="col-lg-5 col-md-10">
                <div class="header-caption">
                  <div class="header-rating rating">
                    <ul class="rating-stars">
                      <li><em class="icon ni ni-star-fill"></em></li>
                      <li><em class="icon ni ni-star-fill"></em></li>
                      <li><em class="icon ni ni-star-fill"></em></li>
                      <li><em class="icon ni ni-star-fill"></em></li>
                      <li><em class="icon ni ni-star-fill"></em></li>
                    </ul>
                    <div class="rating-text">Dịch vụ tăng like mạng xã hội</div>
                  </div>
                  <h1 class="header-title">
                    Dịch vụ tăng like follow, lượt xem cho MXH như Facebook,
                    Instagram, Tiktok, Youtube, Shopee
                  </h1>
                  <div class="header-text">
                    <p>
                      <strong>{{ agencyName }}</strong> Like nhanh nhất Việt Nam
                      <br />
                      chuyên cung cấp các dịch vụ tăng Like, Share, Comment,
                      Follow... cho các Mạng xã hội như Facebook, Instagram,
                      Tikok, Youtube, Shopee giá rẻ và chất lượng nhất
                    </p>
                  </div>
                  <ul class="header-action btns-inline">
                    <li>
                      <a
                        @click="onClickLogin"
                        class="btn btn-primary text-white"
                        ><span>Dùng thử ngay</span></a
                      >
                    </li>
                  </ul>
                </div>
              </div>
            </div>
          </div>
        </div>
        <div class="header-brand pb-4 pt-2 pb-lg-5">
          <div class="container">
            <div class="row align-items-center g-gs">
              <div class="col-4 col-md-2">
                <div class="brand-item">
                  <img
                    alt="Dịch vụ tăng đơn hàng, đánh giá , like shop SHOPEE "
                    src="/assets/images/theme2/shopee.png"
                  />
                </div>
              </div>
              <div class="col-4 col-md-2">
                <div class="brand-item">
                  <img
                    alt="Dịch vụ tăng like buff thả tim comment follow share group facebook "
                    src="/assets/images/theme2/facebook.png"
                  />
                </div>
              </div>
              <div class="col-4 col-md-2">
                <div class="brand-item">
                  <img
                    src="/assets/images/theme2/youtube.png"
                    alt="Dịch vụ buff, tăng sub cho kênh youtube"
                  />
                </div>
              </div>
              <div class="col-4 col-md-2">
                <div class="brand-item">
                  <img
                    src="/assets/images/theme2/instagram.png"
                    alt="dịch vụ buff, tăng like follow cho instagram"
                  />
                </div>
              </div>
              <div class="col-4 col-md-2">
                <div class="brand-item">
                  <img
                    src="/assets/images/theme2/tiktok.png"
                    alt="dịch vụ tăng, thả tim, buff sub follow cho tiktok"
                  />
                </div>
              </div>
            </div>
          </div>
        </div>
      </header>

      <section
        class="section section-service pb-0"
        ref="serviceProvided"
        id="service"
      >
        <div class="container">
          <div class="row justify-content-center text-center">
            <div class="col-sm-7 col-md-6 col-9">
              <div class="section-head">
                <h2 class="title">
                  Chúng tôi cung cấp nhiều loại dịch vụ MXH khác nhau
                </h2>
              </div>
            </div>
          </div>
          <div class="section-content">
            <div class="row justify-content-center text-center g-gs">
              <div class="col-9 col-sm-7 col-md-3">
                <div class="service service-s2">
                  <div class="service-icon styled-icon styled-icon-s2 bg-blue">
                    <em
                      class="icon ni ni-facebook-f"
                      style="font-size: 40px"
                    ></em>
                  </div>
                  <div class="service-text">
                    <h4 class="title">Facebook</h4>
                    <p>
                      Dịch vụ tăng like, lượt thích, lượt theo dõi, hack, buff
                      follow cho người dùng, fanpage Facebook không tụt giá rẻ.
                    </p>
                  </div>
                </div>
              </div>
              <div class="col-9 col-sm-7 col-md-3">
                <div class="service service-s2">
                  <div
                    class="service-icon styled-icon styled-icon-s2 bg-orange"
                  >
                    <em
                      class="icon ni ni-instagram"
                      style="font-size: 40px"
                    ></em>
                  </div>
                  <div class="service-text">
                    <h4 class="title">Instagram</h4>
                    <p>
                      Dịch vụ tăng tim, buff tim bài viết và buff follow, tăng
                      follow trên Instagram không tụt giá rẻ.
                    </p>
                  </div>
                </div>
              </div>
              <div class="col-9 col-sm-7 col-md-3">
                <div class="service service-s2">
                  <div class="service-icon styled-icon styled-icon-s2 bg-dark">
                    <img
                      src="/assets/images/theme2/tiktok-ground.png"
                      style="width: 50%"
                    />
                  </div>
                  <div class="service-text">
                    <h4 class="title">Tiktok</h4>
                    <p>
                      Dịch vụ tăng tim, like buff lượt xem trên TikTok, Doujin
                      không tụt giá rẻ nhất.
                    </p>
                  </div>
                </div>
              </div>
              <div class="col-9 col-sm-7 col-md-3">
                <div class="service service-s2">
                  <div
                    class="service-icon styled-icon styled-icon-s2 bg-danger"
                  >
                    <em
                      class="icon ni ni-youtube-fill"
                      style="font-size: 40px"
                    ></em>
                  </div>
                  <div class="service-text">
                    <h4 class="title">Youtube</h4>
                    <p>
                      Dịch vụ tăng sub follow kênh và tăng lượt xem cho kênh
                      Youtube giá rẻ nhất không tụt.
                    </p>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
      <section class="section section-feature pb-0" ref="featured" id="feature">
        <div class="container">
          <div
            class="row flex-row-reverse align-items-center justify-content-between g-gs"
          >
            <div class="col-lg-5">
              <div class="img-block img-block-s1 right">
                <img src="/assets/images/theme2/banner2.png" alt="img" />
              </div>
            </div>
            <div class="col-lg-6">
              <div class="text-block">
                <h2 class="title">Ưu điểm nổi trội của {{ agencyName }}</h2>
                <p>
                  Trong quá trình phát triển tính năng, sự hài lòng của quý
                  khách là điều quan trọng nhất. Vì thế chúng tôi luôn quan tâm
                  đến chất lượng dịch vụ ổn định và hoàn thiện tốt nhất.
                </p>
                <div class="g-gs">
                  <div class="service service-s3">
                    <div
                      class="service-icon styled-icon styled-icon-s3 text-primary"
                    >
                      <svg
                        xmlns="http://www.w3.org/2000/svg"
                        xmlns:xlink="http://www.w3.org/1999/xlink"
                        version="1.1"
                        id="Layer_1"
                        x="0px"
                        y="0px"
                        viewBox="0 0 512 512"
                        style="enable-background: new 0 0 512 512"
                        xml:space="preserve"
                      >
                        <path
                          style="fill: #ff8c29"
                          d="M486.509,420.091L305.863,239.445c-3.119-3.117-8.173-3.117-11.291,0l-78.28,78.28  c-1.497,1.498-2.338,3.528-2.338,5.646c0,2.117,0.841,4.147,2.338,5.646l180.646,180.645c1.525,1.524,3.566,2.338,5.647,2.338  c0.921,0,1.85-0.159,2.745-0.488c2.919-1.069,4.951-3.735,5.21-6.833l5.461-65.526l65.527-5.462c3.098-0.258,5.764-2.29,6.833-5.208  C489.429,425.564,488.706,422.29,486.509,420.091z"
                        ></path>
                        <path
                          style="fill: #fd6a33"
                          d="M256.697,277.32l-40.405,40.405c-1.497,1.498-2.338,3.528-2.338,5.646  c0,2.117,0.841,4.147,2.338,5.646l180.646,180.645c1.525,1.524,3.566,2.338,5.647,2.338c0.921,0,1.85-0.159,2.745-0.488  c2.919-1.069,4.951-3.735,5.21-6.833l5.461-65.526l2.337-0.195L256.697,277.32z"
                        ></path>
                        <path
                          style="fill: #ff8c29"
                          d="M295.709,317.725l-78.28-78.28c-3.119-3.116-8.173-3.118-11.291,0L25.491,420.091  c-2.198,2.198-2.92,5.474-1.85,8.392c1.069,2.919,3.735,4.951,6.833,5.208l65.528,5.462l5.461,65.526  c0.258,3.098,2.29,5.764,5.209,6.833c0.896,0.329,1.824,0.488,2.745,0.488c2.081,0,4.123-0.814,5.647-2.338l180.645-180.645  c1.497-1.498,2.338-3.528,2.338-5.646C298.046,321.254,297.205,319.224,295.709,317.725z"
                        ></path>
                        <path
                          style="fill: #fd6a33"
                          d="M257.431,279.449L96.133,440.748l5.328,63.932c0.258,3.098,2.29,5.764,5.209,6.833  c0.896,0.329,1.824,0.488,2.745,0.488c2.081,0,4.123-0.814,5.647-2.338l180.646-180.645c1.497-1.498,2.338-3.528,2.338-5.646  c0-2.117-0.841-4.148-2.338-5.646L257.431,279.449z"
                        ></path>
                        <path
                          style="fill: #4acfd9"
                          d="M448.478,158.035l-50.466-42.346l-11.44-64.879c-0.673-3.815-3.987-6.597-7.862-6.597h-65.88  L262.365,1.868c-2.969-2.491-7.296-2.491-10.265,0l-50.465,42.346h-65.879c-3.875,0-7.189,2.781-7.862,6.597l-11.441,64.878  l-50.465,42.346c-2.968,2.491-3.719,6.752-1.782,10.107l32.938,57.053l-11.439,64.877c-0.674,3.816,1.49,7.563,5.131,8.889  l61.906,22.532l32.939,57.053c1.937,3.354,5.999,4.837,9.645,3.511l61.905-22.532l61.905,22.532  c0.897,0.327,1.819,0.482,2.728,0.482c2.786,0,5.455-1.464,6.916-3.993l32.939-57.053l61.906-22.532  c3.64-1.325,5.805-5.073,5.131-8.889l-11.439-64.877l32.939-57.053C452.198,164.787,451.445,160.525,448.478,158.035z"
                        ></path>
                        <path
                          style="fill: #fd6a33"
                          d="M256,68.52c-70.141,0-127.204,57.063-127.204,127.204S185.859,322.927,256,322.927  s127.204-57.063,127.204-127.204S326.141,68.52,256,68.52z"
                        ></path>
                        <path
                          style="fill: #ffffff"
                          d="M347.88,170.301c-1.069-3.29-4.134-5.517-7.593-5.517h-58.921l-18.208-56.038  c-1.069-3.29-4.134-5.517-7.593-5.517s-6.524,2.227-7.593,5.517l-18.208,56.038h-58.922c-3.458,0-6.524,2.227-7.593,5.517  c-1.069,3.289,0.102,6.893,2.901,8.926l47.669,34.633l-18.208,56.039c-1.069,3.289,0.102,6.893,2.901,8.926  c1.399,1.017,3.045,1.525,4.692,1.525c1.647,0,3.293-0.508,4.692-1.525l47.669-34.632l47.668,34.632  c2.798,2.033,6.587,2.033,9.384,0c2.798-2.032,3.969-5.636,2.901-8.926l-18.208-56.039l47.669-34.633  C347.778,177.194,348.948,173.59,347.88,170.301z"
                        ></path>
                        <path
                          style="fill: #0295aa"
                          d="M252.101,1.868l-50.465,42.346h-65.879c-3.875,0-7.189,2.781-7.862,6.597l-11.441,64.878  l-50.465,42.346c-2.968,2.491-3.719,6.752-1.782,10.107l32.938,57.053l-11.439,64.877c-0.674,3.816,1.49,7.563,5.131,8.889  l61.906,22.532l32.939,57.053c1.937,3.354,5.999,4.837,9.645,3.511l60.672-22.083V0.105C254.602,0.324,253.249,0.905,252.101,1.868z  "
                        ></path>
                        <path
                          style="fill: #f0353d"
                          d="M128.796,195.723c0,70.141,57.063,127.204,127.204,127.204V68.52  C185.86,68.52,128.796,125.584,128.796,195.723z"
                        ></path>
                        <path
                          style="fill: #ffd1a9"
                          d="M255.565,103.231c-3.458,0-6.524,2.227-7.593,5.517l-18.208,56.038h-58.922  c-3.458,0-6.524,2.227-7.593,5.517c-1.069,3.289,0.102,6.893,2.901,8.926l47.669,34.633l-18.208,56.039  c-1.069,3.289,0.102,6.893,2.901,8.926c1.399,1.017,3.045,1.525,4.692,1.525c1.647,0,3.293-0.508,4.692-1.525l47.669-34.632  L256,244.51V103.265C255.854,103.258,255.712,103.231,255.565,103.231z"
                        ></path>
                      </svg>
                    </div>
                    <div class="service-text">
                      <h4 class="title">Dịch vụ chất lượng</h4>
                      <p>
                        Cung cấp hầu như đầy đủ tất cả dịch vụ truyền thông xã
                        hội. Điều quan trọng nhất là chất lượng dịch vụ tốt nhất
                        giá rẻ nhất đáp ứng nhu cầu của khách hàng.
                      </p>
                    </div>
                  </div>
                  <div class="service service-s3">
                    <div
                      class="service-icon styled-icon styled-icon-s3 text-success"
                    >
                      <svg
                        xmlns="http://www.w3.org/2000/svg"
                        xmlns:xlink="http://www.w3.org/1999/xlink"
                        version="1.1"
                        id="Layer_1"
                        x="0px"
                        y="0px"
                        viewBox="0 0 496 496"
                        style="enable-background: new 0 0 496 496"
                        xml:space="preserve"
                      >
                        <path
                          style="fill: #ed3432"
                          d="M496,369.6c0,27.2-21.6,46.4-48,46.4H48c-26.4,0-48-19.2-48-46.4V126.4C0,99.2,21.6,80,48,80h400  c26.4,0,48,19.2,48,46.4V369.6z"
                        ></path>
                        <path
                          style="fill: #dd0000"
                          d="M48,80h400c26.4,0,48,19.2,48,46.4v243.2c0,27.2-24.8,46.4-51.2,46.4"
                        ></path>
                        <g>
                          <path
                            style="fill: #cc0202"
                            d="M48,80h400c26.4,0,48,19.2,48,46.4V216"
                          ></path>
                          <path
                            style="fill: #cc0202"
                            d="M496,368.8c0,29.6-21.6,47.2-48,47.2H48c-26.4,0-48-20.8-48-48"
                          ></path>
                        </g>
                        <polygon
                          style="fill: #fdce0c"
                          points="248,159.2 268.8,224 337.6,224 282.4,266.4 303.2,332 248,292 192.8,332.8 213.6,265.6   158.4,224 227.2,224 "
                        ></polygon>
                        <polygon
                          style="fill: #fc9c10"
                          points="268.8,224 248,159.2 227.2,224 224.8,224 286.4,278.4 282.4,264.8 337.6,224 "
                        ></polygon>
                      </svg>
                    </div>
                    <div class="service-text">
                      <h4 class="title">
                        Dịch vụ được thực hiện bởi 100% là người Việt Nam
                      </h4>
                      <p>
                        Chúng tôi sử dụng tài khoản MXH là tài khoản người VIỆT
                        NAM thật, tương tác thật, trên Smartphone Android,
                        Iphone
                      </p>
                    </div>
                  </div>
                  <div class="service service-s3">
                    <div
                      class="service-icon styled-icon styled-icon-s3 text-success"
                    >
                      <svg
                        version="1.1"
                        id="Layer_1"
                        xmlns="http://www.w3.org/2000/svg"
                        xmlns:xlink="http://www.w3.org/1999/xlink"
                        x="0px"
                        y="0px"
                        viewBox="0 0 512 512"
                        style="enable-background: new 0 0 512 512"
                        xml:space="preserve"
                      >
                        <path
                          style="fill: #ecebed"
                          d="M155.036,109.731H30.816c-11.218,0-20.311,9.094-20.311,20.311v77.123
                                                	c0,11.218,9.094,20.311,20.311,20.311h51.026l27.221,19.122v-19.122h45.974c11.218,0,20.311-9.094,20.311-20.311v-77.123
                                                	C175.347,118.825,166.253,109.731,155.036,109.731z"
                        ></path>
                        <path
                          style="fill: #ffa036"
                          d="M213.867,319.119v20.352c0,6.799-4.088,12.932-10.365,15.548l-67.24,28.017
                                                	c-14.206,5.92-23.459,22.007-23.459,37.397v81.091h286.349v-81.091c0-15.389-9.254-31.478-23.458-37.397l-67.24-28.017
                                                	c-6.277-2.615-10.365-8.749-10.365-15.548v-20.352H213.867z"
                        ></path>
                        <path
                          style="fill: #102e4e"
                          d="M495.413,406.328c-18.208-11.27-42.14-18.219-68.422-18.51c-26.28,0.291-50.213,7.24-68.422,18.51
                                                	c-3.633,1.75-6.139,5.466-6.139,9.768v19.412c0,5.984,4.851,10.835,10.835,10.835h21.929c5.984,0,10.835-4.851,10.835-10.835
                                                	v-16.647c9.788-2.08,20.183-3.204,30.961-3.204s21.173,1.124,30.961,3.205v16.647c0,5.985,4.851,10.835,10.835,10.835h21.929
                                                	c5.985,0,10.835-4.851,10.835-10.835v-19.412C501.552,411.793,499.046,408.078,495.413,406.328z"
                        ></path>
                        <path
                          style="fill: #03203b"
                          d="M490.717,446.343h-21.929c-5.985,0-10.835-4.851-10.835-10.835v-16.647
                                                	c-9.788-2.08-20.183-3.205-30.961-3.205s-21.173,1.124-30.961,3.204v16.647c0,5.985-4.851,10.835-10.835,10.835h-21.929
                                                	c-0.243,0-0.485-0.01-0.724-0.027v47.158c0,4.446,3.603,8.049,8.049,8.049h115.348c4.446,0,8.049-3.603,8.049-8.049v-47.636
                                                	C492.956,446.166,491.857,446.343,490.717,446.343z"
                        ></path>
                        <g>
                          <circle
                            style="fill: #ffb118"
                            cx="256.149"
                            cy="58.007"
                            r="47.527"
                          ></circle>
                          <path
                            style="fill: #ffb118"
                            d="M318.574,298.314c0,0,58.699-33.55,58.699-104.985c0-68.72-49.696-126.259-121.125-126.259h-0.159
                                                		c-71.429,0-121.125,57.539-121.125,126.259c0,71.434,58.699,104.985,58.699,104.985"
                          ></path>
                        </g>
                        <g>
                          <path
                            style="fill: #febba0"
                            d="M162.314,168.723h-0.367v30.443c-12.925,0-23.403,10.478-23.403,23.403
                                                		c0,12.925,10.478,23.403,23.403,23.403v17.472c1.126,14.735,8.311,27.853,19.192,35.038l56.574,32.342
                                                		c11.36,7.503,25.173,7.503,36.533,0l56.405-32.342c10.879-7.185,18.233-20.303,19.36-35.038v-17.472
                                                		c12.925,0,23.403-10.478,23.403-23.403s-10.478-23.403-23.403-23.403v-30.443"
                          ></path>
                          <path
                            style="fill: #febba0"
                            d="M298.088,319.119v37.474c0,23.081-18.978,41.966-42.06,41.966l0,0
                                                		c-23.081,0-42.161-18.884-42.161-41.966v-37.474"
                          ></path>
                        </g>
                        <circle
                          style="fill: #ffb118"
                          cx="272.552"
                          cy="278.456"
                          r="15.395"
                        ></circle>
                        <path
                          d="M10.585,511.972h-0.137C4.677,511.972,0,507.295,0,501.525s4.677-10.448,10.448-10.448h0.137
                                                	c5.77,0,10.448,4.677,10.448,10.448S16.355,511.972,10.585,511.972z"
                        ></path>
                        <path
                          d="M501.501,511.972h-0.137c-5.77,0-10.448-4.677-10.448-10.448s4.677-10.448,10.448-10.448h0.137
                                                	c5.77,0,10.448,4.677,10.448,10.448S507.271,511.972,501.501,511.972z"
                        ></path>
                        <path
                          d="M294.08,235.476c-6.44,0-11.679-5.239-11.679-11.678c0-6.44,5.239-11.679,11.679-11.679c6.44,0,11.679,5.239,11.679,11.679
                                                	C305.758,230.237,300.519,235.476,294.08,235.476z"
                        ></path>
                        <path
                          d="M217.875,235.476c-6.44,0-11.679-5.239-11.679-11.678c0-6.44,5.239-11.679,11.679-11.679c6.44,0,11.679,5.239,11.679,11.679
                                                	C229.553,230.237,224.315,235.476,217.875,235.476z"
                        ></path>
                        <path
                          d="M112.545,150.792H45.239c-5.77,0-10.448-4.677-10.448-10.448c0-5.77,4.677-10.448,10.448-10.448h67.306
                                                	c5.77,0,10.448,4.677,10.448,10.448C122.993,146.114,118.315,150.792,112.545,150.792z"
                        ></path>
                        <path
                          d="M112.545,179.051H45.239c-5.77,0-10.448-4.677-10.448-10.448c0-5.77,4.677-10.448,10.448-10.448h67.306
                                                	c5.77,0,10.448,4.678,10.448,10.448C122.993,174.374,118.315,179.051,112.545,179.051z"
                        ></path>
                        <path
                          d="M83.506,207.309H45.239c-5.77,0-10.448-4.677-10.448-10.448c0-5.77,4.677-10.448,10.448-10.448h38.267
                                                	c5.77,0,10.448,4.678,10.448,10.448C93.954,202.632,89.277,207.309,83.506,207.309z"
                        ></path>
                        <path
                          d="M500.513,397.198c-20.369-12.489-46.417-19.528-73.404-19.828c-0.076-0.001-0.155-0.001-0.232,0
                                                	c-11.807,0.132-23.434,1.553-34.485,4.155c-3.834-3.459-8.128-6.236-12.679-8.133l-67.24-28.016
                                                	c-2.39-0.996-3.936-3.313-3.936-5.904v-16.269l27.31-15.659c0.19-0.109,0.377-0.225,0.561-0.346
                                                	c13.674-9.03,22.654-25.09,24.02-42.96c0.021-0.264,0.169-8.957,0.219-9.54c12.363-4.104,21.565-15.157,22.997-28.504
                                                	c2.706-10.602,4.081-21.658,4.081-32.866c0-36.539-12.988-70.637-36.572-96.012c-10.998-11.833-23.903-21.26-38.132-28.056
                                                	c0.731-3.691,1.11-7.451,1.11-11.254c0-31.969-26.009-57.978-57.978-57.978c-31.969,0-57.978,26.009-57.978,57.978
                                                	c0,3.78,0.374,7.516,1.096,11.186c-14.287,6.799-27.242,16.251-38.278,28.123c-0.603,0.649-1.194,1.306-1.782,1.966H30.816
                                                	c-16.96,0-30.758,13.798-30.758,30.758v77.123c0,16.96,13.798,30.758,30.758,30.758h47.724l24.518,17.225
                                                	c1.792,1.26,3.895,1.898,6.006,1.898c1.648,0,3.3-0.39,4.816-1.176c3.46-1.798,5.63-5.372,5.63-9.271v-8.674h12.286
                                                	c4.053,7.924,11.128,14.055,19.704,16.845v8.674c0,0.265,0.01,0.532,0.03,0.796c1.372,17.943,10.288,34.002,23.851,42.96
                                                	c0.187,0.123,0.378,0.24,0.573,0.352l27.466,15.702v16.219c0,2.59-1.545,4.907-3.936,5.904l-67.241,28.017
                                                	c-17.597,7.333-29.887,26.676-29.887,47.04v70.643H44.384c-5.77,0-10.448,4.677-10.448,10.448s4.677,10.448,10.448,10.448h423.179
                                                	c5.77,0,10.448-4.679,10.448-10.448s-4.677-10.448-10.448-10.448h-94.573v-34.285h12.204c11.736,0,21.283-9.547,21.283-21.283
                                                	v-7.914c13.421-1.979,27.6-1.98,41.027,0v7.913c0,11.736,9.547,21.283,21.283,21.283h14.751v13.041
                                                	c0,5.77,4.677,10.448,10.448,10.448s10.448-4.677,10.448-10.448v-18.078c4.62-3.907,7.565-9.736,7.565-16.246v-19.412
                                                	C512,408.183,507.512,400.834,500.513,397.198z M256.148,20.924c20.447,0,37.082,16.635,37.082,37.082
                                                	c0,1.241-0.067,2.475-0.188,3.7c-11.752-3.351-24.134-5.084-36.894-5.084h-0.159c-12.704,0-25.035,1.717-36.74,5.039
                                                	c-0.119-1.21-0.184-2.428-0.184-3.654C219.066,37.559,235.702,20.924,256.148,20.924z M124.417,193.329
                                                	c0,8.017,0.716,15.951,2.104,23.699h-17.458c-5.449,0-9.922,4.17-10.405,9.492l-10.81-7.593c-1.758-1.236-3.855-1.898-6.005-1.898
                                                	H30.816c-5.439,0-9.863-4.425-9.863-9.863v-77.123c0-5.439,4.425-9.863,9.863-9.863h113.13
                                                	C131.232,141.693,124.417,166.87,124.417,193.329z M255.99,77.518h0.159c63.063,0,110.626,49.736,110.676,115.707
                                                	c-2.007-1.156-4.131-2.13-6.369-2.859v-13.285c0-5.77-4.677-10.448-10.448-10.448h-73.33V144.82c0-4.65-3.073-8.741-7.539-10.034
                                                	c-4.466-1.296-9.251,0.519-11.737,4.447l-17.343,27.402h-78.112c-5.77,0-10.448,4.678-10.448,10.448v13.286
                                                	c-2.17,0.706-4.23,1.647-6.184,2.754C145.415,127.202,192.96,77.518,255.99,77.518z M186.639,289.59
                                                	c-7.984-5.406-13.283-15.291-14.245-26.569V245.97c0-5.77-4.678-10.448-10.448-10.448c-6.6,0-12.053-4.965-12.845-11.354
                                                	c0.022-0.61-0.008-1.228-0.097-1.848c0.134-7.028,5.882-12.708,12.942-12.708c5.77,0,10.448-4.678,10.448-10.448v-11.636h73.417
                                                	c3.582,0,6.913-1.834,8.828-4.86l1.599-2.526c1.309,4.276,5.288,7.387,9.992,7.387h73.33v11.637c0,5.77,4.677,10.448,10.448,10.448
                                                	c7.143,0,12.954,5.812,12.954,12.954c0,4.247-2.063,8.012-5.231,10.376c-1.891-1.892-4.504-3.062-7.39-3.062
                                                	c-5.77,0-10.448,4.677-10.448,10.448v5.198c-0.006,0.148-0.021,0.294-0.021,0.443v5.964c-0.221,8.898-7.514,16.073-16.465,16.073
                                                	H296.18c-4.021-9.058-13.096-15.395-23.629-15.395c-14.25,0-25.843,11.593-25.843,25.843c0,14.25,11.593,25.843,25.843,25.843
                                                	c10.532,0,19.607-6.337,23.629-15.395h27.228c0.96,0,1.91-0.048,2.852-0.12c-0.369,0.278-0.739,0.555-1.118,0.812l-56.094,32.165
                                                	c-0.191,0.11-0.377,0.225-0.561,0.346c-7.832,5.173-17.184,5.174-25.017,0c-0.187-0.123-0.377-0.24-0.573-0.352L186.639,289.59z
                                                	 M277.499,278.454c0,2.728-2.22,4.947-4.947,4.947s-4.947-2.22-4.947-4.947s2.22-4.947,4.947-4.947S277.499,275.726,277.499,278.454
                                                	z M287.64,335.185v21.409c0,17.379-14.181,31.518-31.612,31.518c-17.487,0-31.713-14.139-31.713-31.518v-21.395l7.938,4.539
                                                	c7.333,4.763,15.529,7.144,23.725,7.144c8.198,0,16.396-2.383,23.73-7.148L287.64,335.185z M352.096,453.589v37.488H123.251v-70.643
                                                	c0-11.776,7.321-23.707,17.029-27.753l64.007-26.669c4.469,24.419,25.962,42.994,51.742,42.994
                                                	c25.731,0,47.181-18.575,51.642-42.994l58.582,24.408c-4.457,2.04-8.734,4.296-12.78,6.776
                                                	c-6.999,3.635-11.487,10.984-11.487,18.897v19.413C341.985,443.144,346.039,449.833,352.096,453.589z M491.104,435.508
                                                	c0,0.214-0.174,0.388-0.388,0.388h-21.928c-0.214,0-0.388-0.174-0.388-0.388v-16.647c0-4.933-3.451-9.194-8.276-10.22
                                                	c-10.718-2.278-21.865-3.433-33.133-3.433c-11.27,0-22.418,1.155-33.133,3.433c-4.825,1.025-8.275,5.287-8.275,10.219v16.647
                                                	c0,0.214-0.174,0.388-0.388,0.388l-21.949-0.004c-0.204-0.011-0.368-0.177-0.368-0.383v-19.411c0-0.229,0.172-0.329,0.225-0.354
                                                	c0.33-0.159,0.653-0.335,0.964-0.529c17.209-10.651,39.551-16.667,62.923-16.946c23.372,0.279,45.714,6.295,62.923,16.946
                                                	c0.311,0.193,0.633,0.37,0.963,0.529c0.052,0.025,0.226,0.126,0.226,0.355V435.508z"
                        ></path>
                        <path
                          d="M217.443,454.509h-0.158c-5.77,0-10.448-4.677-10.448-10.448c0-5.77,4.678-10.448,10.448-10.448h0.158
                                                	c5.77,0,10.448,4.677,10.448,10.448C227.891,449.832,223.214,454.509,217.443,454.509z"
                        ></path>
                        <path
                          d="M182.532,454.51h-30.489c-5.77,0-10.448-4.677-10.448-10.448s4.678-10.448,10.448-10.448h30.489
                                                	c5.77,0,10.448,4.677,10.448,10.448S188.302,454.51,182.532,454.51z"
                        ></path>
                      </svg>
                    </div>
                    <div class="service-text">
                      <h4 class="title">Hỗ trợ nhiệt tình</h4>
                      <p>
                        Hỗ trợ nhanh chóng, giải đáp và tư vấn, tiếp nhận dịch
                        vụ tự động nhanh nhất giúp khách hàng xử lý đơn hàng
                        nhanh nhất có thể.
                      </p>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
      <section class="section section-feature">
        <div class="container">
          <div class="row align-items-center justify-content-between g-gs">
            <div class="col-lg-5">
              <div class="img-block img-block-s1 left">
                <img src="/assets/images/theme2/banner3.png" alt="img" />
              </div>
            </div>
            <div class="col-lg-6">
              <div class="text-block">
                <h2 class="title">
                  Lợi ích to lớn của việc tăng tương tác MXH
                </h2>
                <p class="lead">
                  Nếu bạn đang kinh doanh các sản phẩm dịch vụ trên Facebook
                  chắc chắn bạn rất quan tâm đến việc tăng like Facebook. Dịch
                  vụ tăng like Facebook đang cực kỳ phát triển bởi những giá trị
                  mà dịch vụ này mang lại:
                </p>
                <ul>
                  <li>
                    - Trang cá nhân, fanpage của ai càng có nhiều lượt like càng
                    chứng tỏ độ uy tín của trang đó với người xem. Điều đó có
                    nghĩa rằng họ được rất nhiều người theo dõi trên Facebook.
                    Sự nổi tiếng của họ sẽ ngày càng tăng lên.
                  </li>
                  <li>
                    - Với trang fanpage cộng đồng, càng có nhiều người like càng
                    có nhiều người cùng đam mê, cùng sở thích quan tâm.
                  </li>
                  <li>
                    - Trang cá nhân, fanpage có nhiều lượt like theo dõi tạo độ
                    uy tín và niềm tin với những người dùng khác. Từ đó giúp bạn
                    sẽ dễ dàng thu hút đầu tư, hợp tác và dễ bán hàng hơn.
                  </li>
                </ul>
              </div>
            </div>
          </div>
        </div>
      </section>
      <section
        class="section section-pricing bg-lighter"
        ref="priceList"
        id="pricing"
      >
        <div class="container">
          <div class="row justify-content-center">
            <div class="col-xl-4 col-md-5 col-sm-7">
              <div class="section-head text-center">
                <h2 class="title">Bảng giá dịch vụ</h2>
              </div>
            </div>
          </div>
          <div
            class="row justify-content-center justify-content-lg-between align-items-center text-center g-gs"
            id="grid-pricing"
          >
            <div class="pricing mx-1 pricing-s1 card card-shadow round-xl">
              <div class="card-inner card-inner-lg">
                <h2 class="pricing-amount">
                  <svg
                    fill="#000000"
                    xmlns="http://www.w3.org/2000/svg"
                    viewbox="0 0 50 50"
                    width="50px"
                    height="50px"
                  >
                    <path
                      d="M 9 4 C 6.2495759 4 4 6.2495759 4 9 L 4 41 C 4 43.750424 6.2495759 46 9 46 L 41 46 C 43.750424 46 46 43.750424 46 41 L 46 9 C 46 6.2495759 43.750424 4 41 4 L 9 4 z M 9 6 L 41 6 C 42.671576 6 44 7.3284241 44 9 L 44 41 C 44 42.671576 42.671576 44 41 44 L 9 44 C 7.3284241 44 6 42.671576 6 41 L 6 9 C 6 7.3284241 7.3284241 6 9 6 z M 26.042969 10 A 1.0001 1.0001 0 0 0 25.042969 10.998047 C 25.042969 10.998047 25.031984 15.873262 25.021484 20.759766 C 25.016184 23.203017 25.009799 25.64879 25.005859 27.490234 C 25.001922 29.331679 25 30.496833 25 30.59375 C 25 32.409009 23.351421 33.892578 21.472656 33.892578 C 19.608867 33.892578 18.121094 32.402853 18.121094 30.539062 C 18.121094 28.675273 19.608867 27.1875 21.472656 27.1875 C 21.535796 27.1875 21.663054 27.208245 21.880859 27.234375 A 1.0001 1.0001 0 0 0 23 26.240234 L 23 22.039062 A 1.0001 1.0001 0 0 0 22.0625 21.041016 C 21.906673 21.031216 21.710581 21.011719 21.472656 21.011719 C 16.223131 21.011719 11.945313 25.289537 11.945312 30.539062 C 11.945312 35.788589 16.223131 40.066406 21.472656 40.066406 C 26.72204 40.066409 31 35.788588 31 30.539062 L 31 21.490234 C 32.454611 22.653646 34.267517 23.390625 36.269531 23.390625 C 36.542588 23.390625 36.802305 23.374442 37.050781 23.351562 A 1.0001 1.0001 0 0 0 37.958984 22.355469 L 37.958984 17.685547 A 1.0001 1.0001 0 0 0 37.03125 16.6875 C 33.886609 16.461891 31.379838 14.012216 31.052734 10.896484 A 1.0001 1.0001 0 0 0 30.058594 10 L 26.042969 10 z M 27.041016 12 L 29.322266 12 C 30.049047 15.2987 32.626734 17.814404 35.958984 18.445312 L 35.958984 21.310547 C 33.820114 21.201935 31.941489 20.134948 30.835938 18.453125 A 1.0001 1.0001 0 0 0 29 19.003906 L 29 30.539062 C 29 34.707538 25.641273 38.066406 21.472656 38.066406 C 17.304181 38.066406 13.945312 34.707538 13.945312 30.539062 C 13.945312 26.538539 17.066083 23.363182 21 23.107422 L 21 25.283203 C 18.286416 25.535721 16.121094 27.762246 16.121094 30.539062 C 16.121094 33.483274 18.528445 35.892578 21.472656 35.892578 C 24.401892 35.892578 27 33.586491 27 30.59375 C 27 30.64267 27.001859 29.335571 27.005859 27.494141 C 27.009759 25.65271 27.016224 23.20692 27.021484 20.763672 C 27.030884 16.376775 27.039186 12.849206 27.041016 12 z"
                    />
                  </svg>
                  <br />TikTok
                </h2>
                <h5 class="pricing-title">Dịch vụ TikTok</h5>
                <ul class="pricing-features list list-nostyle">
                  <li>Đang phát triển</li>
                </ul>
                <div class="pricing-action">
                  <a
                    @click="onClickLogin"
                    class="btn btn-primary btn-lg text-white btn-block"
                    ><span>Mua Ngay</span></a
                  >
                </div>
              </div>
            </div>
            <div
              class="pricing mx-1 pricing-featured pricing-s1 card card-shadow round-xl"
            >
              <div class="card-inner card-inner-lg">
                <h2 class="pricing-amount">
                  <svg
                    version="1.1"
                    style="width: 50px; height: 50px"
                    id="Capa_1"
                    xmlns="http://www.w3.org/2000/svg"
                    xmlns:xlink="http://www.w3.org/1999/xlink"
                    x="0px"
                    y="0px"
                    viewBox="0 0 455.73 455.73"
                    xml:space="preserve"
                  >
                    <path
                      style="fill: #ffffff; width: 50px; height: 50px"
                      d="M0,0v455.73h242.704V279.691h-59.33v-71.864h59.33v-60.353c0-43.893,35.582-79.475,79.475-79.475
                                          h62.025v64.622h-44.382c-13.947,0-25.254,11.307-25.254,25.254v49.953h68.521l-9.47,71.864h-59.051V455.73H455.73V0H0z"
                    ></path>
                  </svg>
                  Facebook
                </h2>
                <h5 class="pricing-title">Dịch vụ Facebook</h5>
                <ul class="pricing-features list list-nostyle">
                  <li>Gói Sub/Follow 7đ/lượt</li>
                  <li>Gói Like Fanpage 7đ/lượt</li>
                  <li>Gói Buff Like 3đ/lượt</li>
                  <li>Gói Buff Comment 29đ/lượt</li>
                  <li>Gói Buff View Adbreak 4đ/lượt</li>
                  <li>Gói VIP Like 1000đ/lượt</li>
                </ul>
                <div class="pricing-action">
                  <a href="/dang-nhap" class="btn btn-primary btn-lg btn-block"
                    ><span>Mua Ngay</span></a
                  >
                </div>
              </div>
            </div>

            <div class="pricing mx-1 pricing-s1 card card-shadow round-xl">
              <div class="card-inner card-inner-lg">
                <h2 class="pricing-amount">
                  <svg
                    xmlns="http://www.w3.org/2000/svg"
                    xmlns:xlink="http://www.w3.org/1999/xlink"
                    version="1.1"
                    id="Layer_1"
                    x="0px"
                    y="0px"
                    width="50px"
                    height="50px"
                    viewBox="0 0 492 490"
                  >
                    <g>
                      <g>
                        <g>
                          <path
                            d="M245,135c-60.654,0-110,49.346-110,110s49.346,110,110,110s110-49.346,110-110S305.654,135,245,135z M245,335     c-49.626,0-90-40.374-90-90c0-49.626,40.374-90,90-90c49.626,0,90,40.374,90,90C335,294.626,294.626,335,245,335z"
                          ></path>
                          <path
                            d="M355,90c-19.299,0-35,15.701-35,35s15.701,35,35,35s35-15.701,35-35S374.299,90,355,90z M355,140     c-8.272,0-15-6.729-15-15s6.728-15,15-15c8.272,0,15,6.729,15,15S363.272,140,355,140z"
                          ></path>
                          <path
                            d="M245,175c-38.598,0-70,31.402-70,70c0,38.598,31.402,70,70,70c38.598,0,70-31.402,70-70C315,206.402,283.598,175,245,175     z M245,295c-27.57,0-50-22.43-50-50s22.43-50,50-50s50,22.43,50,50S272.57,295,245,295z"
                          ></path>
                          <path
                            d="M340,45H150C94.86,45,50,89.86,50,145v195c0,55.14,44.86,100,100,100h190c55.141,0,100-44.86,100-100V145     C440,89.86,395.141,45,340,45z M420,340c0,44.112-35.888,80-80,80H150c-44.112,0-80-35.888-80-80V145c0-44.112,35.888-80,80-80     h190c44.112,0,80,35.888,80,80V340z"
                          ></path>
                          <path
                            d="M390,0H100C44.86,0,0,44.86,0,100v290c0,55.14,44.86,100,100,100h290c55.141,0,100-44.86,100-100V100     C490,44.86,445.141,0,390,0z M470,390c0,44.112-35.888,80-80,80H100c-44.112,0-80-35.888-80-80V100c0-44.112,35.888-80,80-80h290     c44.112,0,80,35.888,80,80V390z"
                          ></path>
                        </g>
                      </g>
                    </g>
                  </svg>
                  Instagram
                </h2>
                <h5 class="pricing-title">Dịch vụ Instagram</h5>
                <ul class="pricing-features list list-nostyle">
                  <li>Đang phát triển</li>
                </ul>
                <div class="pricing-action">
                  <a
                    @click="onClickLogin"
                    class="btn btn-primary btn-lg text-white btn-block"
                    ><span>Mua Ngay</span></a
                  >
                </div>
              </div>
            </div>

            <div class="pricing mx-1 pricing-s1 card card-shadow round-xl">
              <div class="card-inner card-inner-lg">
                <h2 class="pricing-amount">
                  <svg
                    version="1.1"
                    id="Capa_1"
                    xmlns="http://www.w3.org/2000/svg"
                    xmlns:xlink="http://www.w3.org/1999/xlink"
                    x="0px"
                    y="0px"
                    viewbox="0 0 49 49"
                    width="50px"
                    height="50px"
                    xml:space="preserve"
                  >
                    <g>
                      <g>
                        <path
                          d="M39.256,6.5H9.744C4.371,6.5,0,10.885,0,16.274v16.451c0,5.39,4.371,9.774,9.744,9.774h29.512
                c5.373,0,9.744-4.385,9.744-9.774V16.274C49,10.885,44.629,6.5,39.256,6.5z M47,32.726c0,4.287-3.474,7.774-7.744,7.774H9.744
                C5.474,40.5,2,37.012,2,32.726V16.274C2,11.988,5.474,8.5,9.744,8.5h29.512c4.27,0,7.744,3.488,7.744,7.774V32.726z"
                        />
                        <path
                          d="M33.36,24.138l-13.855-8.115c-0.308-0.18-0.691-0.183-1.002-0.005S18,16.527,18,16.886v16.229
                c0,0.358,0.192,0.69,0.502,0.868c0.154,0.088,0.326,0.132,0.498,0.132c0.175,0,0.349-0.046,0.505-0.137l13.855-8.113
                c0.306-0.179,0.495-0.508,0.495-0.863S33.667,24.317,33.36,24.138z M20,31.37V18.63l10.876,6.371L20,31.37z"
                        />
                      </g>
                    </g>
                  </svg>
                  Youtube
                </h2>
                <h5 class="pricing-title">Dịch vụ Youtube</h5>
                <ul class="pricing-features list list-nostyle">
                  <li>Đang phát triển</li>
                </ul>
                <div class="pricing-action">
                  <a
                    @click="onClickLogin"
                    class="btn btn-primary btn-lg text-white btn-block"
                    ><span>Mua Ngay</span></a
                  >
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
      <section
        class="section section-testimonial pb-0"
        ref="reviewers"
        id="reviews"
      >
        <div class="container">
          <div class="row justify-content-center text-center">
            <div class="col-xl-7 col-md-8 col-10">
              <div class="section-head">
                <h2 class="title">Khách hàng nói gì về chúng tôi</h2>
              </div>
            </div>
          </div>
          <div class="row g-gs justify-content-center">
            <div class="col-lg-4">
              <div class="card card-shadow round-xl">
                <div class="card-inner card-inner-lg">
                  <div class="review review-s2">
                    <div class="review-portrait review-portrait-s1">
                      <div class="portrait portrait-s1">
                        <img src="/assets/images/theme2/khach5.jpg" alt />
                      </div>
                    </div>
                    <div class="review-content">
                      <div class="review-rating rating rating-sm">
                        <ul class="rating-stars">
                          <li><em class="icon ni ni-star-fill"></em></li>
                          <li><em class="icon ni ni-star-fill"></em></li>
                          <li><em class="icon ni ni-star-fill"></em></li>
                          <li><em class="icon ni ni-star-fill"></em></li>
                          <li><em class="icon ni ni-star-fill"></em></li>
                        </ul>
                      </div>
                      <div class="review-text">
                        <p>
                          Tôi đã dùng dịch vụ ở nhiều nơi nhưng ở
                          {{ agencyName }} thật sự làm tôi hài lòng bởi đội ngũ
                          trẻ và nhiệt tình
                        </p>
                        <h6 class="review-name text-dark">Thảo Nguyên</h6>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="col-lg-4">
              <div class="card card-shadow round-xl">
                <div class="card-inner card-inner-lg">
                  <div class="review review-s2">
                    <div class="review-portrait review-portrait-s1">
                      <div class="portrait portrait-s1">
                        <img src="/assets/images/theme2/khach2.jpg" alt />
                      </div>
                    </div>
                    <div class="review-content">
                      <div class="review-rating rating rating-sm">
                        <ul class="rating-stars">
                          <li><em class="icon ni ni-star-fill"></em></li>
                          <li><em class="icon ni ni-star-fill"></em></li>
                          <li><em class="icon ni ni-star-fill"></em></li>
                          <li><em class="icon ni ni-star-fill"></em></li>
                          <li><em class="icon ni ni-star-fill"></em></li>
                        </ul>
                      </div>
                      <div class="review-text">
                        <p>
                          Thật sự thì mình chưa tìm được trang mua like nào rẻ
                          hơn {{ agencyName }} và có dịch vụ tốt hơn
                          {{ agencyName }}.
                        </p>
                        <h6 class="review-name text-dark">Hoàng Tuấn</h6>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
            <div class="col-lg-4">
              <div class="card card-shadow round-xl">
                <div class="card-inner card-inner-lg">
                  <div class="review review-s2">
                    <div class="review-portrait review-portrait-s1">
                      <div class="portrait portrait-s1">
                        <img src="/assets/images/theme2/khach6.jpg" alt />
                      </div>
                    </div>
                    <div class="review-content">
                      <div class="review-rating rating rating-sm">
                        <ul class="rating-stars">
                          <li><em class="icon ni ni-star-fill"></em></li>
                          <li><em class="icon ni ni-star-fill"></em></li>
                          <li><em class="icon ni ni-star-fill"></em></li>
                          <li><em class="icon ni ni-star-fill"></em></li>
                          <li><em class="icon ni ni-star-fill"></em></li>
                        </ul>
                      </div>
                      <div class="review-text">
                        <p>
                          Tôi rất hài lòng về dịch vụ của {{ agencyName }}.
                          Ngoài ra khi tôi gặp vấn đề gì về Fb đều được các bạn
                          hỗ trợ.
                        </p>
                        <h6 class="review-name text-dark">Thu Hường</h6>
                      </div>
                    </div>
                  </div>
                </div>
              </div>
            </div>
          </div>
        </div>
      </section>
      <footer class="footer bg-lighter" id="footer">
        <div class="container">
          <div
            class="row g-3 align-items-center justify-content-md-between py-4 py-md-5"
          >
            <div class="col-md-3">
              <div class="footer-logo">
                <a href="/" class="logo-link" v-if="agencyName">
                  <template>
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
                    <span class="font-logo">{{ agencyName }}</span>
                  </template>
                </a>
                <a href="/" class="logo-link" v-else>
                  <img
                    class="logo-light logo-img"
                    src="/assets/images/theme2/logo.svg"
                    alt="logo"
                  />
                  <img
                    class="logo-dark logo-img"
                    src="/assets/images/theme2/logo.svg"
                    alt="logo-dark"
                  />
                </a>
              </div>
            </div>
            <div class="col-md-9 d-flex justify-content-md-end">
              <ul class="link-inline gx-4">
                <li><a href="#">How it works</a></li>
                <li><a href="#">Service</a></li>
                <li><a href="#">Help</a></li>
                <li><a href="#">Contact</a></li>
              </ul>
            </div>
          </div>
          <hr class="hr border-light mb-0 mt-n1" />
          <div
            class="row g-3 align-items-center justify-content-md-between py-4"
          >
            <div class="col-md-8">
              <div class="text-base">Copyright © 2021 {{ agencyName }}.</div>
            </div>
            <div class="col-md-4 d-flex justify-content-md-end">
              <ul class="social">
                <li>
                  <a href="#"><em class="icon ni ni-twitter"></em></a>
                </li>
                <li>
                  <a href="#"><em class="icon ni ni-facebook-f"></em></a>
                </li>
                <li>
                  <a href="#"><em class="icon ni ni-instagram"></em></a>
                </li>
                <li>
                  <a href="#"><em class="icon ni ni-pinterest"></em></a>
                </li>
              </ul>
            </div>
          </div>
        </div>
      </footer>
    </div>
  </div>
</template>
<script setup lang="ts">
import { onBeforeMount, onBeforeUnmount, onMounted, ref } from "vue";
import { getAgencyName } from "@/base/functions/commonFns";
import { useRouter } from "vue-router";
import { getLocalStorage } from "@/base/functions/localStorageFns";
import { ThemeNameDefault, ThemeColor } from "@/commons/constants/theme-config";

const router = useRouter();
const headerRef = ref<any>(null);
const landingPage = ref<any>(null);
const overView = ref();
const reviewers = ref();
const serviceProvided = ref();
const featured = ref();
const priceList = ref();
const position = ref<any>([]);
const activeClass = ref(1);
const mobileMenuBtn = ref(null);
const agencyName = ref("");

const handleScroll = () => {
  position.value = [
    Math.floor(landingPage.value.offsetHeight),
    Math.floor(serviceProvided.value.offsetHeight) + position.value[0],
    Math.floor(featured.value.offsetHeight) + position.value[1],
    Math.floor(priceList.value.offsetHeight) + position.value[2],
    Math.floor(reviewers.value.offsetHeight) + position.value[3],
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
    landingPage.value.scrollTop > featured.value.offsetTop
  ) {
    activeClass.value = 3;
  }
  if (
    position.value[3] - landingPage.value.scrollTop > 0 &&
    landingPage.value.scrollTop > priceList.value.offsetTop
  ) {
    activeClass.value = 4;
  }
  if (
    position.value[4] - landingPage.value.scrollTop > 0 &&
    landingPage.value.scrollTop > reviewers.value.offsetTop
  ) {
    activeClass.value = 5;
  }
};

const scrollIntoView = (key: any) => {
  activeClass.value = key;
  switch (key) {
    case 1:
      landingPage.value.scrollTo({
        top: 0,
        behavior: "smooth",
      });
      break;
    case 2:
      serviceProvided.value.scrollIntoView({
        behavior: "smooth",
      });
      break;
    case 3:
      featured.value.scrollIntoView({
        behavior: "smooth",
      });
      break;
    case 4:
      priceList.value.scrollIntoView({
        behavior: "smooth",
      });
      break;

    default:
      reviewers.value.scrollIntoView({
        behavior: "smooth",
      });
      break;
  }
  if (mobileMenuBtn.value.classList.contains("active")) {
    mobileMenuBtn.value.click();
  }
  setTimeout(() => {
    activeClass.value = key;
  }, 800);
};

const jsApps = [
  { id: "nio-app-bundle", path: "/assets/scriptApp/bundle.js" },
  // {id: 'js-rocket-loader', path:'/assets/scriptApp/rocket-loader.min.js'},
  // {id: 'nio-app-script', path:'/assets/scriptApp/scripts.js'},
];

let scrollEvent: any = null;

onBeforeMount(() => {
  // Kiểm tra đã có token chưa - nếu chưa thì điều hướng ra login
  const themeName =
    getLocalStorage(localStorage.AutoLike_Theme) || ThemeNameDefault;
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
  jsApps.map((_item) => {
    const script = document.createElement("script");
    script.id = _item.id;
    script.src = _item.path;
    document.body.appendChild(script);
  });
  agencyName.value = getAgencyName();
  scrollEvent = landingPage.value.addEventListener(
    "scroll",
    () => {
      if (landingPage.value.scrollTop != 0) {
        headerRef.value.classList.add("is-transparenting");
      } else {
        headerRef.value.classList.remove("is-transparenting");
      }
      handleScroll();
    },
    true
  );
});

onBeforeUnmount(() => {
  const nioAppBundle = document.getElementById("nio-app-bundle");
  if (nioAppBundle) {
    nioAppBundle.remove();
  }
  const nioAppScript = document.getElementById("nio-app-script");
  if (nioAppScript) {
    nioAppScript.remove();
  }
  const rkLoader = document.getElementById("js-rocket-loader");
  if (rkLoader) {
    rkLoader.remove();
  }

  landingPage.value
    ? landingPage.value.removeEventListener("scroll", scrollEvent)
    : "";
});

function onClickLogin() {
  router.push("/login");
}
</script>
<style src="" scoped>
@import "@/assets/themes/theme2/css/styleLandingPageTheme2.css";
@import "@/assets/themes/theme2/css/theme.css";
.nk-app-root {
  width: 100%;
  overflow: auto;
  height: 100%;
}
.pointer {
  cursor: pointer;
}
#grid-pricing {
  display: grid;
  grid-template-columns: 1fr;
}
.is-transparenting {
  position: fixed;
  top: 0;
  z-index: 10;
  transform: translate3d(0px, 0px, 0px);
  padding: 0.5rem;
  width: 100%;
  background: #fff;
  box-shadow: 0 1px 3px 2px rgba(31, 43, 58, 0.08);
  transition: background-color 0.4s ease-out, padding 0.4s;
}
@media (min-width: 576px) {
  #grid-pricing {
    display: grid;
    grid-template-columns: 1fr;
  }
}

@media (min-width: 768px) {
  .card-inner-lg {
    padding: 1rem;
  }
  #grid-pricing {
    display: grid;
    grid-template-columns: 1fr 1fr;
  }
}
@media (min-width: 1200px) {
  #grid-pricing {
    display: grid;
    grid-template-columns: 1fr 1fr 1fr 1fr;
  }
}
.mobile-menu {
  height: 100rem !important;
}
.logo-2 {
  fill: var(--color-active-sidebar);
}
</style>
