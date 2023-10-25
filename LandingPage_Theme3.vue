<template>
  <div id="landing-page-3" ref="landingPage">
    <!-- NAVBAR -->
    <nav
      class="navbar navbar-expand-lg navbar-light bg-white navbar-reponsive"
      ref="navbar"
    >
      <div class="container">
        <!-- Brand -->
        <template v-if="agencyName">
          <a class="navbar-brand" href="/">
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
          </a>
        </template>
        <a class="navbar-brand" href="/" v-else>
          <img
            src="/assets/images/theme2/logo.svg"
            class="navbar-brand-img"
            alt="..."
          />
        </a>

        <!-- Toggler -->
        <button
          class="navbar-toggler"
          type="button"
          data-bs-toggle="collapse"
          data-bs-target="#navbarCollapse"
          aria-controls="navbarCollapse"
          aria-expanded="false"
          aria-label="Toggle navigation"
        >
          <span class="navbar-toggler-icon"></span>
        </button>

        <!-- Collapse -->
        <div
          class="collapse navbar-collapse"
          id="navbarCollapse"
          ref="mobileMenuBar"
        >
          <!-- Toggler -->
          <button
            class="navbar-toggler"
            ref="closeBtn"
            type="button"
            data-bs-toggle="collapse"
            data-bs-target="#navbarCollapse"
            aria-controls="navbarCollapse"
            aria-expanded="false"
            aria-label="Toggle navigation"
          >
            <svg
              xmlns="http://www.w3.org/2000/svg"
              height="1em"
              viewBox="0 0 352 512"
            >
              <!--! Font Awesome Free 6.4.0 by @fontawesome - https://fontawesome.com License - https://fontawesome.com/license (Commercial License) Copyright 2023 Fonticons, Inc. -->
              <path
                d="M242.72 256l100.07-100.07c12.28-12.28 12.28-32.19 0-44.48l-22.24-22.24c-12.28-12.28-32.19-12.28-44.48 0L176 189.28 75.93 89.21c-12.28-12.28-32.19-12.28-44.48 0L9.21 111.45c-12.28 12.28-12.28 32.19 0 44.48L109.28 256 9.21 356.07c-12.28 12.28-12.28 32.19 0 44.48l22.24 22.24c12.28 12.28 32.2 12.28 44.48 0L176 322.72l100.07 100.07c12.28 12.28 32.2 12.28 44.48 0l22.24-22.24c12.28-12.28 12.28-32.19 0-44.48L242.72 256z"
              />
            </svg>
          </button>

          <!-- Navigation -->
          <ul class="navbar-nav ms-auto">
            <li class="nav-item dropdown" @click.prevent="scrollIntoView(1)">
              <a
                class="nav-link dropdown-toggle"
                data-bs-toggle="dropdown"
                href="#"
                aria-haspopup="true"
                aria-expanded="false"
              >
                Trang chủ
              </a>
            </li>
            <li class="nav-item dropdown" @click.prevent="scrollIntoView(2)">
              <a
                class="nav-link dropdown-toggle"
                data-bs-toggle="dropdown"
                href="#"
                aria-haspopup="true"
                aria-expanded="false"
              >
                Giới thiệu
              </a>
            </li>
            <li class="nav-item dropdown" @click.prevent="scrollIntoView(3)">
              <a
                class="nav-link dropdown-toggle"
                data-bs-toggle="dropdown"
                href="#"
                aria-haspopup="true"
                aria-expanded="false"
              >
                Cấp bậc
              </a>
            </li>
          </ul>

          <div class="d-flex justify-content-center lift ms-auto navbar-btn">
            <div class="mb-5 mb-md-0">
              <a class="btn btn-sm btn-primary btn-nav" @click="onClickLogin">
                Đăng nhập
              </a>
            </div>
          </div>
        </div>
      </div>
    </nav>

    <!-- WELCOME -->
    <section class="pt-4 pt-md-11 mt-10 mt-md-0" ref="welcome">
      <div class="container">
        <div class="row align-items-center">
          <div class="col-12 col-md-5 col-lg-6 order-md-2">
            <!-- Image -->
            <img
              src="https://cdn.mypanel.link/9b5331/wmsnx0xpekkkhxwr.webp"
              class="img-fluid mw-md-150 mw-lg-130 mb-6 mb-md-0"
              alt="..."
              data-aos="fade-up"
              data-aos-delay="100"
            />
          </div>
          <div class="col-12 col-md-7 col-lg-6 order-md-1" data-aos="fade-up">
            <!-- Heading -->
            <h1 class="display-3 text-center text-md-start">
              Website dịch vụ mạng xã hội tốt nhất
            </h1>

            <!-- Text -->
            <p class="lead text-center text-md-start text-muted mb-6 mb-lg-8">
              Những Gì Bạn Cần Tăng - Chúng Tôi Có Cung Cấp Phát triển mọi nền
              tảng mạng xã hội của bạn với dịch vụ của chúng tôi.
            </p>

            <!-- Buttons -->
            <div class="text-center text-md-start">
              <a @click="onClickLogin" class="btn btn-primary shadow lift me-1">
                Đăng nhập
              </a>
            </div>
          </div>
        </div>
        <!-- / .row -->
      </div>
      <!-- / .container -->
    </section>

    <!-- FEATURES -->
    <section class="py-8 py-md-11 border-bottom" ref="featured">
      <div class="container">
        <div class="row">
          <div class="col-12 col-md-4" data-aos="fade-up">
            <!-- Icon -->
            <div class="icon text-primary mb-3">
              <svg
                width="24"
                height="24"
                viewBox="0 0 24 24"
                xmlns="http://www.w3.org/2000/svg"
              >
                <g fill="none" fill-rule="evenodd">
                  <path d="M0 0h24v24H0z" />
                  <path
                    d="M7 3h10a4 4 0 110 8H7a4 4 0 110-8zm0 6a2 2 0 100-4 2 2 0 000 4z"
                    fill="#335EEA"
                  />
                  <path
                    d="M7 13h10a4 4 0 110 8H7a4 4 0 110-8zm10 6a2 2 0 100-4 2 2 0 000 4z"
                    fill="#335EEA"
                    opacity=".3"
                  />
                </g>
              </svg>
            </div>

            <!-- Heading -->
            <h3 class="mt-4">Chất lượng ấn tượng</h3>

            <!-- Text -->
            <p class="text-muted mb-6 mb-md-0">
              Hệ thống được vận hành hoàn toàn tự động 24/24.
            </p>
          </div>
          <div class="col-12 col-md-4" data-aos="fade-up" data-aos-delay="50">
            <!-- Icon -->
            <div class="icon text-primary mb-3">
              <svg
                width="24"
                height="24"
                viewBox="0 0 24 24"
                xmlns="http://www.w3.org/2000/svg"
              >
                <g fill="none" fill-rule="evenodd">
                  <path d="M0 0h24v24H0z" />
                  <path
                    d="M5.5 4h4A1.5 1.5 0 0111 5.5v1A1.5 1.5 0 019.5 8h-4A1.5 1.5 0 014 6.5v-1A1.5 1.5 0 015.5 4zm9 12h4a1.5 1.5 0 011.5 1.5v1a1.5 1.5 0 01-1.5 1.5h-4a1.5 1.5 0 01-1.5-1.5v-1a1.5 1.5 0 011.5-1.5z"
                    fill="#335EEA"
                  />
                  <path
                    d="M5.5 10h4a1.5 1.5 0 011.5 1.5v7A1.5 1.5 0 019.5 20h-4A1.5 1.5 0 014 18.5v-7A1.5 1.5 0 015.5 10zm9-6h4A1.5 1.5 0 0120 5.5v7a1.5 1.5 0 01-1.5 1.5h-4a1.5 1.5 0 01-1.5-1.5v-7A1.5 1.5 0 0114.5 4z"
                    fill="#335EEA"
                    opacity=".3"
                  />
                </g>
              </svg>
            </div>

            <!-- Heading -->
            <h3 class="mt-4">Tạo sự nổi tiếng trên mạng xã hội</h3>

            <!-- Text -->
            <p class="text-muted mb-6 mb-md-0">
              Khiến bạn trở nên nổi bật hơn, thu hút hơn và phổ biến hơn trên
              các trang mạng xã hội
            </p>
          </div>
          <div class="col-12 col-md-4" data-aos="fade-up" data-aos-delay="100">
            <!-- Icon -->
            <div class="icon text-primary mb-3">
              <svg
                width="24"
                height="24"
                viewBox="0 0 24 24"
                xmlns="http://www.w3.org/2000/svg"
              >
                <g fill="none" fill-rule="evenodd">
                  <path d="M0 0h24v24H0z" />
                  <path
                    d="M17.272 8.685a1 1 0 111.456-1.37l4 4.25a1 1 0 010 1.37l-4 4.25a1 1 0 01-1.456-1.37l3.355-3.565-3.355-3.565zm-10.544 0L3.373 12.25l3.355 3.565a1 1 0 01-1.456 1.37l-4-4.25a1 1 0 010-1.37l4-4.25a1 1 0 011.456 1.37z"
                    fill="#335EEA"
                  />
                  <rect
                    fill="#335EEA"
                    opacity=".3"
                    transform="rotate(15 12 12)"
                    x="11"
                    y="4"
                    width="2"
                    height="16"
                    rx="1"
                  />
                </g>
              </svg>
            </div>

            <!-- Heading -->
            <h3 class="mt-4">Công nghệ</h3>

            <!-- Text -->
            <p class="text-muted mb-0">
              Hệ thống được vận hành hoàn toàn tự động 24/24.
            </p>
          </div>
        </div>
        <!-- / .row -->
      </div>
      <!-- / .container -->
    </section>

    <!-- SHAPE -->
    <div class="position-relative mt-n8">
      <div class="shape shape-bottom shape-fluid-x text-gray-200">
        <svg
          viewBox="0 0 2880 480"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            fill-rule="evenodd"
            clip-rule="evenodd"
            d="M2160 0C1440 240 720 240 720 240H0v240h2880V0h-720z"
            fill="currentColor"
          />
        </svg>
      </div>
    </div>

    <!-- STATS -->
    <section class="pt-12 pt-md-13 bg-gray-200" ref="stats">
      <div class="container">
        <div class="row align-items-center">
          <div class="col-12 col-md-5 col-lg-6 order-md-2">
            <!-- Image -->
            <img
              src="https://cdn.mypanel.link/9b5331/oixw7dqlyshrnp0e.webp"
              alt="..."
              class="img-fluid mb-6 mb-md-0"
            />
          </div>
          <div class="col-12 col-md-7 col-lg-6 order-md-1">
            <!-- Heading -->
            <h2>
              <span class="text-primary"
                >Vì Sao Nên Chọn Dịch Vụ Của Chúng Tôi ?</span
              >
            </h2>

            <!-- Text -->
            <p class="fs-lg text-gray-700 mb-6">
              <b class="fw-bold"> {{ agencyName }} </b> tự hào là một trong
              những Webste cung cấp tài khoản dịch vụ về nền tảng mạng xã hội
              Online hàng đầu Việt Nam. Chúng tôi đã có hơn 5 năm kinh nghiệm
              trong các lĩnh vực này. Với đội ngũ nhân viên chuyên nghiệp chúng
              tôi cam kết sẽ đem lại cho Quý Khách những dịch vụ chất lượng hơn
              cả mong đợi, an toàn và uy tín.
            </p>

            <!-- Stats -->
            <div class="d-flex">
              <div class="pe-5">
                <h3 class="mb-0">
                  <span>{{ count }}</span
                  >+
                </h3>
                <p class="text-gray-700 mb-0">Khách hàng</p>
              </div>
              <div class="border-start border-gray-300"></div>
              <div class="px-5">
                <h3 class="mb-0">
                  <span>24</span>/
                  <span>7</span>
                </h3>
                <p class="text-gray-700 mb-0">Hỗ trợ</p>
              </div>
              <div class="border-start border-gray-300"></div>
              <div class="ps-5">
                <h3 class="mb-0">
                  <span>{{ count }}</span
                  >+
                </h3>
                <p class="text-gray-700 mb-0">Đối tác</p>
              </div>
            </div>
          </div>
        </div>
        <!-- / .row -->
      </div>
      <!-- / .container -->
    </section>

    <!-- PRICING -->
    <section class="pt-9 pt-md-12 bg-gray-200 align-items-center" ref="pricing">
      <div class="col-10 mx-auto">
        <div class="row justify-content-center">
          <div class="col-12 col-md-10 col-lg-8 text-center">
            <!-- Heading -->
            <h1>Cấp bậc ưu đãi khách hàng</h1>
          </div>
        </div>
        <!-- / .row -->
        <div class="row align-items-center">
          <div class="col-12 col-md-4">
            <!-- Card -->
            <div
              class="card rounded-lg shadow-lg mb-6 mb-md-0"
              style="z-index: 1"
              data-aos="fade-up"
            >
              <!-- Body -->
              <div class="card-body py-6">
                <div class="row justify-content-center">
                  <div class="col-12 col-xl-9">
                    <!-- Badge -->
                    <div class="text-center mb-5">
                      <span class="badge rounded-pill bg-primary-soft">
                        <span class="h6 fw-bold text-uppercase"
                          >Cộng tác viên</span
                        >
                      </span>
                    </div>

                    <!-- Price -->
                    <div class="d-flex justify-content-center">
                      <span
                        class="price display-2 mb-0"
                        data-annual="29"
                        data-monthly="49"
                        >500,000</span
                      >
                      <span class="h4 align-self-end mb-1">VNĐ</span>
                    </div>

                    <!-- Text -->
                    <p class="text-center text-muted mb-6 mb-md-8"></p>

                    <!-- Features -->
                    <div class="d-flex">
                      <!-- Check -->
                      <div
                        class="badge badge-rounded-circle bg-success-soft mt-1 me-4"
                      >
                        <i class="fe fe-check"></i>
                      </div>

                      <!-- Text -->
                      <p>Tạo Một Tài Khoản</p>
                    </div>
                    <div class="d-flex">
                      <!-- Check -->
                      <div
                        class="badge badge-rounded-circle bg-success-soft mt-1 me-4"
                      >
                        <i class="fe fe-check"></i>
                      </div>

                      <!-- Text -->
                      <p>Nạp Tiền Vào Tài Khoản</p>
                    </div>
                    <div class="d-flex">
                      <!-- Check -->
                      <div
                        class="badge badge-rounded-circle bg-success-soft mt-1 me-4"
                      >
                        <i class="fe fe-check"></i>
                      </div>

                      <!-- Text -->
                      <p>Mua Hàng</p>
                    </div>
                    <div class="d-flex">
                      <!-- Check -->
                      <div
                        class="badge badge-rounded-circle bg-success-soft mt-1 me-4"
                      >
                        <i class="fe fe-check"></i>
                      </div>

                      <!-- Text -->
                      <p>Tận hưởng kết quả tuyệt vời</p>
                    </div>
                  </div>
                </div>
                <!-- / .row -->
              </div>

              <!-- Button -->
              <a
                @click="onClickLogin"
                class="card-btn btn w-100 btn-lg btn-primary"
              >
                Bắt đầu ngay
              </a>
            </div>
          </div>
          <div class="col-12 col-md-4 mx-auto">
            <div
              class="card rounded-lg shadow-lg mb-6 mb-md-0"
              style="z-index: 1"
              data-aos="fade-up"
            >
              <!-- Body -->
              <div class="card-body py-6">
                <div class="row justify-content-center">
                  <div class="col-12 col-xl-9">
                    <!-- Badge -->
                    <div class="text-center mb-5">
                      <span class="badge rounded-pill bg-primary-soft">
                        <span class="h6 fw-bold text-uppercase">Đại lý</span>
                      </span>
                    </div>

                    <!-- Price -->
                    <div class="d-flex justify-content-center">
                      <span
                        class="price display-2 mb-0"
                        data-annual="29"
                        data-monthly="49"
                        >5,000,000</span
                      >
                      <span class="h4 align-self-end mb-1">VNĐ</span>
                    </div>

                    <!-- Text -->
                    <p class="text-center text-muted mb-6 mb-md-8"></p>

                    <!-- Features -->
                    <div class="d-flex">
                      <!-- Check -->
                      <div
                        class="badge badge-rounded-circle bg-success-soft mt-1 me-4"
                      >
                        <i class="fe fe-check"></i>
                      </div>

                      <!-- Text -->
                      <p>Tạo Một Tài Khoản</p>
                    </div>
                    <div class="d-flex">
                      <!-- Check -->
                      <div
                        class="badge badge-rounded-circle bg-success-soft mt-1 me-4"
                      >
                        <i class="fe fe-check"></i>
                      </div>

                      <!-- Text -->
                      <p>Nạp Tiền Vào Tài Khoản</p>
                    </div>
                    <div class="d-flex">
                      <!-- Check -->
                      <div
                        class="badge badge-rounded-circle bg-success-soft mt-1 me-4"
                      >
                        <i class="fe fe-check"></i>
                      </div>

                      <!-- Text -->
                      <p>Mua Hàng</p>
                    </div>
                    <div class="d-flex">
                      <!-- Check -->
                      <div
                        class="badge badge-rounded-circle bg-success-soft mt-1 me-4"
                      >
                        <i class="fe fe-check"></i>
                      </div>

                      <!-- Text -->
                      <p>Tận hưởng kết quả tuyệt vời</p>
                    </div>
                  </div>
                </div>
                <!-- / .row -->
              </div>

              <!-- Button -->
              <a
                @click="onClickLogin"
                class="card-btn btn w-100 btn-lg btn-success"
              >
                Bắt đầu ngay
              </a>
            </div>
          </div>
          <div class="col-12 col-md-4">
            <div
              class="card rounded-lg shadow-lg mb-6 mb-md-0"
              style="z-index: 1"
              data-aos="fade-up"
            >
              <!-- Body -->
              <div class="card-body py-6">
                <div class="row justify-content-center">
                  <div class="col-12 col-xl-9">
                    <!-- Badge -->
                    <div class="text-center mb-5">
                      <span class="badge rounded-pill bg-primary-soft">
                        <span class="h6 fw-bold text-uppercase"
                          >Nhà phân phối</span
                        >
                      </span>
                    </div>

                    <!-- Price -->
                    <div class="d-flex justify-content-center">
                      <span
                        class="price display-2 mb-0"
                        data-annual="29"
                        data-monthly="49"
                        >100,000,000</span
                      >
                      <span class="h4 align-self-end mb-1">VNĐ</span>
                    </div>

                    <!-- Text -->
                    <p class="text-center text-muted mb-6 mb-md-8"></p>

                    <!-- Features -->
                    <div class="d-flex">
                      <!-- Check -->
                      <div
                        class="badge badge-rounded-circle bg-success-soft mt-1 me-4"
                      >
                        <i class="fe fe-check"></i>
                      </div>

                      <!-- Text -->
                      <p>Tạo Một Tài Khoản</p>
                    </div>
                    <div class="d-flex">
                      <!-- Check -->
                      <div
                        class="badge badge-rounded-circle bg-success-soft mt-1 me-4"
                      >
                        <i class="fe fe-check"></i>
                      </div>

                      <!-- Text -->
                      <p>Nạp Tiền Vào Tài Khoản</p>
                    </div>
                    <div class="d-flex">
                      <!-- Check -->
                      <div
                        class="badge badge-rounded-circle bg-success-soft mt-1 me-4"
                      >
                        <i class="fe fe-check"></i>
                      </div>

                      <!-- Text -->
                      <p>Mua Hàng</p>
                    </div>
                    <div class="d-flex">
                      <!-- Check -->
                      <div
                        class="badge badge-rounded-circle bg-success-soft mt-1 me-4"
                      >
                        <i class="fe fe-check"></i>
                      </div>

                      <!-- Text -->
                      <p>Tận hưởng kết quả tuyệt vời</p>
                    </div>
                  </div>
                </div>
                <!-- / .row -->
              </div>

              <!-- Button -->
              <a
                @click="onClickLogin"
                class="card-btn btn w-100 btn-lg btn-danger"
              >
                Bắt đầu ngay
              </a>
            </div>
          </div>
        </div>
        <!-- / .row -->
      </div>
    </section>

    <!-- SHAPE -->
    <div class="position-relative mt-n15">
      <div class="shape shape-bottom shape-fluid-x text-dark">
        <svg
          viewBox="0 0 2880 48"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M0 48h2880V0h-720C1442.5 52 720 0 720 0H0v48z"
            fill="currentColor"
          />
        </svg>
      </div>
    </div>

    <!-- FAQ -->
    <section class="pt-15 bg-dark">
      <div class="container pt-8 pt-md-11">
        <div class="row">
          <div class="col-12 col-md-6">
            <!-- Item -->
            <div class="d-flex">
              <!-- Badge -->
              <div class="badge badge-lg badge-rounded-circle bg-success">
                <span>?</span>
              </div>

              <div class="ms-5">
                <!-- Heading -->
                <h4 class="text-white">
                  Tôi có thể nạp tiền qua những phương thức nào?
                </h4>

                <!-- Text -->
                <p class="text-muted mb-6 mb-md-8">
                  Trên web hỗ trợ phương thức nạp tiền qua ví điện tử Momo,
                  Chuyển khoản ngân hàng, nạp bằng thẻ cào , Thẻ Siêu Rẻ và các
                  phương thức nạp tiền khác, Hãy nạp tiền thông qua phương thức
                  thanh toán mà bạn thích nhất.
                </p>
              </div>
            </div>

            <!-- Item -->
            <div class="d-flex">
              <!-- Badge -->
              <div class="badge badge-lg badge-rounded-circle bg-success">
                <span>?</span>
              </div>

              <div class="ms-5">
                <!-- Heading -->
                <h4 class="text-white">
                  Tôi có thể tìm thấy những loại dịch vụ nào?
                </h4>

                <!-- Text -->
                <p class="text-muted mb-6 mb-md-0">
                  Chúng tôi cung cấp các dịch vụ Mạng Xã Hội , Dịch vụ mua bán
                  tài khoản , dịch vụ website và các dịch vụ liên quan khác.
                </p>
              </div>
            </div>
          </div>
          <div class="col-12 col-md-6">
            <!-- Item -->
            <div class="d-flex">
              <!-- Badge -->
              <div class="badge badge-lg badge-rounded-circle bg-success">
                <span>?</span>
              </div>

              <div class="ms-5">
                <!-- Heading -->
                <h4 class="text-white">
                  Tôi có bị khóa tài khoản nếu mua dịch vụ MXH không?
                </h4>

                <!-- Text -->
                <p class="text-muted mb-6 mb-md-8">
                  Dịch vụ chúng tôi cung cấp là 100% an toàn! Tài khoản của bạn
                  sẽ không bị khóa.
                </p>
              </div>
            </div>

            <!-- Item -->
            <div class="d-flex">
              <!-- Badge -->
              <div class="badge badge-lg badge-rounded-circle bg-success">
                <span>?</span>
              </div>

              <div class="ms-5">
                <!-- Heading -->
                <h4 class="text-white">Tôi có thể nhận hỗ trợ ở đâu?</h4>

                <!-- Text -->
                <p class="text-muted mb-6 mb-md-0">
                  Bạn có thể nhận hỗ trợ tại zalo , telegram hoặc facebook ,...
                </p>
              </div>
            </div>
          </div>
        </div>
        <!-- / .row -->
      </div>
      <!-- / .container -->
    </section>

    <!-- CTA -->
    <section class="py-8 py-md-11 bg-dark">
      <div class="container">
        <div class="row justify-content-center">
          <div class="col-12 col-md-10 col-lg-8 text-center">
            <!-- Badge -->
            <span class="badge rounded-pill bg-gray-700-soft mb-4">
              <span class="h6 fw-bold text-uppercase">Bắt đầu ngay</span>
            </span>

            <!-- Heading -->
            <h1 class="display-4 text-white">Bạn còn chờ đợi gì nữa?</h1>

            <!-- Text -->
            <p class="fs-lg text-muted mb-6 mb-md-8">
              Hãy sử dụng thử dịch vụ của chúng tôi nhé.
            </p>

            <!-- Button -->
            <a @click="onClickLogin" class="btn btn-success lift">
              Đăng nhập
              <svg
                xmlns="http://www.w3.org/2000/svg"
                height="1em"
                viewBox="0 0 448 512"
                fill="#efeff1"
              >
                <path
                  d="M190.5 66.9l22.2-22.2c9.4-9.4 24.6-9.4 33.9 0L441 239c9.4 9.4 9.4 24.6 0 33.9L246.6 467.3c-9.4 9.4-24.6 9.4-33.9 0l-22.2-22.2c-9.5-9.5-9.3-25 .4-34.3L311.4 296H24c-13.3 0-24-10.7-24-24v-32c0-13.3 10.7-24 24-24h287.4L190.9 101.2c-9.8-9.3-10-24.8-.4-34.3z"
                />
              </svg>
            </a>
          </div>
        </div>
        <!-- / .row -->
      </div>
      <!-- / .container -->
    </section>

    <!-- SHAPE -->
    <div class="position-relative">
      <div class="shape shape-bottom shape-fluid-x text-gray-200">
        <svg
          viewBox="0 0 2880 48"
          fill="none"
          xmlns="http://www.w3.org/2000/svg"
        >
          <path
            d="M0 48h2880V0h-720C1442.5 52 720 0 720 0H0v48z"
            fill="currentColor"
          />
        </svg>
      </div>
    </div>
    <!--  FOOTER-->
    <footer class="footer bg-lighter" id="footer">
      <div class="container">
        <div
          class="row g-3 align-items-center justify-content-md-between py-4 py-md-5"
        >
          <div class="col-md-3">
            <div class="footer-logo">
              <template v-if="agencyName">
                <a class="logo-link" href="/">
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
                  class="logo-dark logo-img"
                  src="/assets/images/theme2/logo.svg"
                  alt="logo-dark"
                />
              </a>
            </div>
          </div>
          <div class="col-md-9 d-flex justify-content-md-end">
            <ul class="link-inline gx-4 mt-4 mt-md-0">
              <li class="mx-2 text-success"><a href="#">How it works</a></li>
              <li class="mx-2 text-success"><a href="#">Service</a></li>
              <li class="mx-2 text-success"><a href="#">Help</a></li>
              <li class="mx-2 text-success"><a href="#">Contact</a></li>
            </ul>
          </div>
        </div>
        <hr class="hr border-light mb-0 mt-n1" />
        <div class="row g-3 align-items-center justify-content-md-between py-4">
          <div class="col-md-8">
            <div class="text-base">Copyright © 2021 {{ agencyName }}.</div>
          </div>
          <div class="col-md-4 d-flex justify-content-md-end">
            <ul class="list-unstyled list-inline list-social mb-6 mb-md-0">
              <li class="list-inline-item list-social-item me-3">
                <a href="#!" class="text-decoration-none">
                  <img
                    src="/assets/images/theme3/instagram.svg"
                    class="list-social-icon"
                    alt="..."
                  />
                </a>
              </li>
              <li class="list-inline-item list-social-item me-3">
                <a href="#!" class="text-decoration-none">
                  <img
                    src="/assets/images/theme3/facebook.svg"
                    class="list-social-icon"
                    alt="..."
                  />
                </a>
              </li>
              <li class="list-inline-item list-social-item me-3">
                <a href="#!" class="text-decoration-none">
                  <img
                    src="/assets/images/theme3/telegram.svg"
                    class="list-social-icon"
                    alt="..."
                  />
                </a>
              </li>
              <li class="list-inline-item list-social-item">
                <a href="#!" class="text-decoration-none">
                  <img
                    src="/assets/images/theme3//youtube.svg"
                    class="list-social-icon"
                    alt="..."
                  />
                </a>
              </li>
            </ul>
          </div>
        </div>
      </div>
    </footer>
  </div>
</template>
<script setup lang="ts">
import { onBeforeUnmount, onMounted, ref, watch } from "@vue/runtime-core";
import { useRouter } from "vue-router";
import { getAgencyName } from "@/base/functions/commonFns";
import { onBeforeMount } from "vue";
import { getLocalStorage } from "@/base/functions/localStorageFns";
import { LocalStorageKey } from "@/commons/constants/localstorage-key";
import { ThemeNameDefault, ThemeColor } from "@/commons/constants/theme-config";

const landingPage = ref<any>(null);
const navbar = ref();
const welcome = ref();
const featured = ref();
const stats = ref();
const pricing = ref();
const position = ref<any>([]);
const animateClass = ref(0);
const featElements = ref([]);
const pricingElements = ref([]);
const welcomeElements = ref([]);
const count = ref(0);
const hour = ref(24);
const day = ref(7);
const router = useRouter();
const agencyName = ref("");
const handleScroll = () => {
  position.value = [
    Math.floor(landingPage.value.offsetHeight),
    Math.floor(welcome.value.offsetHeight) + position.value[0],
    Math.floor(featured.value.offsetHeight) + position.value[1],
    Math.floor(stats.value.offsetHeight) + position.value[2],
    Math.floor(pricing.value.offsetHeight) + position.value[3],
  ];
  if (
    position.value[0] - landingPage.value.scrollTop > 0 &&
    landingPage.value.scrollTop > welcome.value.offsetTop
  ) {
    animateClass.value = 1;
  }
  if (
    position.value[1] - landingPage.value.scrollTop > 0 &&
    landingPage.value.scrollTop > featured.value.offsetTop
  ) {
    animateClass.value = 2;
  }
  if (
    position.value[2] - landingPage.value.scrollTop > 0 &&
    landingPage.value.scrollTop > stats.value.offsetTop
  ) {
    animateClass.value = 3;
  }
  if (
    position.value[3] - landingPage.value.scrollTop > 0 &&
    landingPage.value.scrollTop > pricing.value.offsetTop
  ) {
    animateClass.value = 4;
  }
};

const closeBtn = ref(null);
const mobileMenuBar = ref(null);
const scrollIntoView = (key: any) => {
  switch (key) {
    case 1:
      welcome.value.scrollIntoView({
        behavior: "smooth",
      });
      break;
    case 2:
      stats.value.scrollIntoView({
        behavior: "smooth",
      });
      break;
    default:
      pricing.value.scrollIntoView({
        behavior: "smooth",
      });
      break;
  }
  if (mobileMenuBar.value.classList.contains("show")) {
    closeBtn.value.click();
  }
};

watch(animateClass, (val) => {
  if (val == 1 || val == 2) {
    // call feature animate
    if (val == 1) count.value = 999;
    featElements.value.forEach(($el) => {
      $el.classList.add("aos-animate");
    });
    pricingElements.value.forEach(($el) => {
      $el.classList.remove("aos-animate");
    });
  }
  if (val == 2) {
    // call stats animate
    let currentValue = 0;
    const finalValue = 999;
    const duration = 1300; // 1.3 seconds
    const interval = duration / finalValue;

    const timer = setInterval(() => {
      currentValue++;
      count.value = currentValue;

      if (currentValue === finalValue) {
        clearInterval(timer);
      }
    }, interval);
  }
  if (val == 3) {
    // call stats animate
    count.value = 999;
    pricingElements.value.forEach(($el) => {
      $el.classList.add("aos-animate");
    });
    featElements.value.forEach(($el) => {
      $el.classList.remove("aos-animate");
    });
  }
});

const jsApps = [
  { id: "bundjs", path: "/assets/scriptApp/vendor.bundle.js" },
  { id: "themejs", path: "/assets/scriptApp/theme.bundle.js" },
];

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
  jsApps.map((_item) => {
    const script = document.createElement("script");
    script.id = _item.id;
    script.src = _item.path;
    document.body.appendChild(script);
  });

  agencyName.value = getAgencyName();
  landingPage.value.addEventListener(
    "scroll",
    () => {
      handleScroll();
    },
    true
  );

  featElements.value = featured.value.querySelectorAll('[data-aos="fade-up"]');
  pricingElements.value = pricing.value.querySelectorAll(
    '[data-aos="fade-up"]'
  );
  welcomeElements.value = welcome.value.querySelectorAll(
    '[data-aos="fade-up"]'
  );
  welcomeElements.value.forEach(($el) => {
    $el.classList.add("aos-animate");
  });
});

onBeforeUnmount(() => {
  jsApps.map((_item) => {
    const script = document.getElementById(_item.id);
    if (script) {
      script.remove();
    }
  });
});

function onClickLogin() {
  router.push("/login");
}
</script>
<style src="@/assets/themes/theme3/scss/style.scss" scoped lang="scss">
::-webkit-scrollbar {
  width: 0 !important;
  /* background-color: #F5F5F5; */
}
@media (min-width: 576px) {
}

@media (min-width: 768px) {
}
@media (min-width: 1200px) {
}
.logo-2 {
  fill: var(--color-active-sidebar);
}
</style>
