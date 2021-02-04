<template>
  <header id="header">
    <div class="container h-100">
      <div class="row h-100 align-items-center align-content-center">
        <div class="col-lg-6 order-lg-0 order-1">
          <h1 class="title fw-bold mb-3"></h1>
          <p class="h6 description text-secondary"></p>

          <div class=" text-lg-start text-center">
            <a href="#portfolio" class="btn border-btn mb-5 me-4 bg-primary">
              My Portfolio
            </a>
            <a
              class="btn border-btn mb-5 text-decoration-none text-white"
              href="../assets/cv/Hassan Mostafa ( Front End Develoeper ).pdf"
              download=""
              >Get My CV
            </a>
            <div class="contact w-100">
              <ul class=" list-unstyled">
                <li>
                  <a
                    href="https://www.facebook.com/profile.php?id=100028549263026"
                    ><i class="fab fa-facebook-f"></i
                  ></a>
                </li>
                <li>
                  <a href="https://www.linkedin.com/in/js-developer-a36564205/"
                    ><i class="fab fa-linkedin-in"></i
                  ></a>
                </li>
                <li>
                  <a href="https://wa.me/01558795604"
                    ><i class="fab fa-whatsapp"></i
                  ></a>
                </li>
              </ul>
            </div>
          </div>
        </div>
        <div class="col-lg-6 order-lg-1 order-0 mb-3 mb-lg-0">
          <img
            src="../assets/img/header.svg"
            alt=""
            class="img-fluid w-100 animate"
          />
        </div>
      </div>
    </div>
  </header>
</template>

<script>
import Typed from "typed.js";

export default {
  data() {
    return {
      title: 'Hi I am <span class="text-primary">Hassan Mostafa</span>',
      description: `I am a Front End Developer With More Than 1 Year Experience <br />
            Working with the Latest Technologies like scss pug and Framework
            vue.js <br />
            Creating websites is not just a work for me, I love writing code and
            learning new stuff.`,
    };
  },

  mounted() {
    new Typed(".title", {
      strings: [this.title],
      typeSpeed: 50,
      showCursor: false,
    });

    new Typed(".description", {
      strings: [this.description],
      typeSpeed: 10,
      startDelay: 2100,
      showCursor: false,
    });
  },
};
</script>
