<template>
  <div class="main">
    <ScrollTop :is-scroll="isScroll"></ScrollTop>
    <Navbar @click-contact="clickContact" @click-projects="clickProjects" />

    <div class="section-one">
      <div class="section-one__container">
        <div class="section-one__container__wrapper">
          <div class="section-one__container__wrapper__text">
            <div class="section-one__container__wrapper__text__position">
              <div></div>
              <div>Front-End Developer</div>
            </div>
            <div class="section-one__container__wrapper__text__name">
              Ahmad Raihan Akhdani
            </div>
            <div class="section-one__container__wrapper__text__desc">
              Hi, I’m Raihan. I’m Frontend Web Developer based in Yogyakarta,
              Indonesia. I'm passionate about cutting-edge, pixel-perfect,
              beautiful interfaces and intuitively implemented UX.
            </div>
            <div class="section-one__container__wrapper__text__touch">
              <a
                target="_blank"
                href="https://www.linkedin.com/in/ahmad-raihan-akhdani-202104154/"
              >
                <img src="/images/linkedin.png" />
              </a>
              <a target="_blank" href="https://github.com/ahmadraihann">
                <img src="/images/github.png" />
              </a>
              <a
                target="_blank"
                href="https://www.instagram.com/ahmad.rayhann/?hl=id"
              >
                <img src="/images/instagram.png" />
              </a>
            </div>
            <div class="section-one__container__wrapper__text__button">
              <Button
                variant="outlined"
                label="Get In Touch"
                @btn-click="clickContact"
              ></Button>
              <Button
                variant="text"
                label="Projects"
                @btn-click="clickProjects"
              ></Button>
            </div>
            <div class="section-one__container__wrapper__text__line"></div>
            <div class="section-one__container__wrapper__text__open">
              I am currently open for part-time work.
            </div>
          </div>
          <div class="section-one__container__wrapper__image">
            <div class="section-one__container__wrapper__image__wrapper">
              <img src="/images/profile.png" />
            </div>
            <div class="section-one__container__wrapper__image__line"></div>
            <div class="section-one__container__wrapper__image__button">
              <Button
                variant="outlined"
                label="Get In Touch"
                @btn-click="clickContact"
              ></Button>
              <Button
                variant="text"
                label="Projects"
                @btn-click="clickProjects"
              ></Button>
            </div>
            <div class="section-one__container__wrapper__image__open">
              I am currently open for part-time work.
            </div>
          </div>
        </div>
      </div>
    </div>

    <section id="projects">
      <div class="section-two">
        <div class="section-two__container">
          <div class="section-two__container__title">Projects</div>
          <div class="section-two__container__tab">
            <v-tabs
              v-model="tab"
              bg-color="transparent"
              color="basil"
              align-tabs="center"
              class="tab-title"
            >
              <v-tab value="all"
                ><div class="section-two__container__tab__text">All</div></v-tab
              >
              <v-tab value="react"
                ><div class="section-two__container__tab__text">
                  React
                </div></v-tab
              >
              <v-tab value="vue"
                ><div class="section-two__container__tab__text">Vue</div></v-tab
              >
            </v-tabs>
            <v-window v-model="tab">
              <v-window-item value="all">
                <div
                  v-for="(item, key) in dataAllProjects"
                  :key="key"
                  class="projects-container"
                >
                  <div class="projects-container__image">
                    <img :src="`/images/${item.image}`" />
                  </div>
                  <div class="projects-container__text">
                    <div class="projects-container__text__title">
                      {{ item.title }}
                    </div>
                    <div class="projects-container__text__desc">
                      {{ item.description }}
                    </div>
                    <div class="projects-container__text__tools">
                      <div class="projects-container__text__tools__wrapper">
                        <div v-for="(element, index) in item.icon" :key="index">
                          <img :src="`/images/${element}`" />
                        </div>
                      </div>
                      <Button
                        variant="outlined"
                        label="Website"
                        append-icon="mdi-arrow-right"
                        @click="openInNewTab(item.url)"
                      ></Button>
                    </div>
                  </div>
                </div>
              </v-window-item>

              <v-window-item value="react">
                <div
                  v-for="(item, key) in dataReactProjects"
                  :key="key"
                  class="projects-container"
                >
                  <div class="projects-container__image">
                    <img :src="`/images/${item.image}`" />
                  </div>
                  <div class="projects-container__text">
                    <div class="projects-container__text__title">
                      {{ item.title }}
                    </div>
                    <div class="projects-container__text__desc">
                      {{ item.description }}
                    </div>
                    <div class="projects-container__text__tools">
                      <div class="projects-container__text__tools__wrapper">
                        <div v-for="(element, index) in item.icon" :key="index">
                          <img :src="`/images/${element}`" />
                        </div>
                      </div>
                      <Button
                        variant="outlined"
                        label="Website"
                        append-icon="mdi-arrow-right"
                      ></Button>
                    </div>
                  </div>
                </div>
              </v-window-item>

              <v-window-item value="vue">
                <div
                  v-for="(item, key) in dataVueProjects"
                  :key="key"
                  class="projects-container"
                >
                  <div class="projects-container__image">
                    <img :src="`/images/${item.image}`" />
                  </div>
                  <div class="projects-container__text">
                    <div class="projects-container__text__title">
                      {{ item.title }}
                    </div>
                    <div class="projects-container__text__desc">
                      {{ item.description }}
                    </div>
                    <div class="projects-container__text__tools">
                      <div class="projects-container__text__tools__wrapper">
                        <div v-for="(element, index) in item.icon" :key="index">
                          <img :src="`/images/${element}`" />
                        </div>
                      </div>
                      <Button
                        variant="outlined"
                        label="View"
                        append-icon="mdi-arrow-right"
                      ></Button>
                    </div>
                  </div>
                </div>
              </v-window-item>
            </v-window>
          </div>
        </div>
      </div>
    </section>

    <section id="contact">
      <Footer />
    </section>
  </div>
</template>

<script lang="ts" setup>
import axios from "axios";

interface typeProjects {
  title: string;
  description: string;
  image: string;
  icon: string[];
  type: string;
  url: string;
}

const tab = ref(null);
const isScroll = ref(false);
const dataAllProjects = reactive<typeProjects[]>([
  { title: "", description: "", image: "", icon: [""], type: "", url: "" },
]);
const dataReactProjects = reactive<typeProjects[]>([
  { title: "", description: "", image: "", icon: [""], type: "", url: "" },
]);
const dataVueProjects = reactive<typeProjects[]>([
  { title: "", description: "", image: "", icon: [""], type: "", url: "" },
]);

const handleGetDataProjects = async () => {
  dataAllProjects.splice(0, 1);
  dataReactProjects.splice(0, 1);
  dataVueProjects.splice(0, 1);

  try {
    const response = await axios({
      method: "get",
      url: "/json/projects.json",
    });

    const data = response.data;

    data.forEach((item: typeProjects) => {
      dataAllProjects.push(item);
      if (item.type === "react") {
        dataReactProjects.push(item);
      } else if (item.type === "vue") {
        dataVueProjects.push(item);
      }
    });
  } catch (error) {
    console.log("");
  }
};

handleGetDataProjects();

const clickProjects = () => {
  const app = document.getElementById("projects") as unknown as HTMLElement;
  app.scrollIntoView({ behavior: "smooth" });
};

const clickContact = () => {
  const app = document.getElementById("contact") as unknown as HTMLElement;
  app.scrollIntoView({ behavior: "smooth" });
};

const doScroll = () => {
  if (window.scrollY > 50) {
    isScroll.value = true;
  } else {
    isScroll.value = false;
  }
};

onMounted(() => {
  window.addEventListener("scroll", doScroll);
});

onUnmounted(() => {
  window.removeEventListener("scroll", doScroll);
});

const openInNewTab = (url: string) => {
  window.open(url, "_blank", "noreferrer");
};
</script>

<style lang="scss" scoped>
@use "@/public/scss/abstracts/global" as *;
.bg-basil {
  background-color: #e63946 !important;
}
.text-basil {
  color: #e63946 !important;
}

.main {
  .section-one {
    background: #ffffff;
    margin-top: 100px;
    &__container {
      max-width: $max-width;
      margin: auto;
      padding: 3px 20px 0 20px;
      &__wrapper {
        display: flex;
        gap: 80px;
        &__text {
          flex: 1;
          color: #ffffff;
          &__position {
            display: flex;
            align-items: center;
            gap: 10px;
            margin: 0 0 54px 0;
            div {
              &:nth-child(1) {
                background: #e63946;
                width: 102px;
                border: 1px solid #e63946;
              }
              &:nth-child(2) {
                font-family: "Inter";
                font-style: normal;
                font-weight: 500;
                font-size: 20px;
                line-height: 28px;
                color: #e63946;
              }
            }
          }
          &__name {
            font-family: "Inter";
            font-style: normal;
            font-weight: 700;
            font-size: 72px;
            line-height: 72px;
            color: #1f2937;
            margin: 0 0 40px 0;
          }
          &__desc {
            font-family: "Inter";
            font-style: normal;
            font-weight: 400;
            font-size: 18px;
            line-height: 28px;
            color: #6b7280;
            margin: 0 0 20px 0;
          }
          &__touch {
            display: flex;
            gap: 10px;
            margin-bottom: 40px;
            img {
              cursor: pointer;
              width: 30px;
            }
          }
          &__button {
            display: flex;
            gap: 20px;
            margin-bottom: 40px;
          }
          &__line {
            background: #6b7280;
            border: 1px solid #e5e7eb;
            width: 100%;
            margin-bottom: 20px;
          }
          &__open {
            font-family: "Inter";
            font-style: normal;
            font-weight: 400;
            font-size: 12px;
            line-height: 16px;
            color: #6b7280;
          }
        }
        &__image {
          flex: 1;
          max-width: 478px;
          width: 100%;
          display: flex;
          justify-content: center;
          align-items: center;
          &__wrapper {
            width: 100%;
            background-image: url("/images/background-pattern.svg");
            background-position: center center;
            background-repeat: no-repeat;
            background-size: cover;
            padding: 20px 20px 0 20px;
            border-radius: 10px;
          }
          img {
            width: 100%;
            display: block;
          }
          &__button {
            display: none;
          }
          &__line {
            display: none;
          }
          &__open {
            display: none;
          }
        }
      }
    }
  }

  .section-two {
    max-width: $max-width;
    margin: 0 auto 100px auto;
    padding: 150px 0 0 0;
    &__container {
      padding: 0 20px;
      &__title {
        margin: 0 auto 50px auto;
        font-family: "Raleway";
        font-style: normal;
        font-weight: 700;
        font-size: 48px;
        line-height: 56px;
        text-align: center;
        letter-spacing: -0.01em;
        text-transform: capitalize;
        color: #2d2d2d;
      }
      &__tab {
        color: #b6b6b6;
        &__text {
          text-transform: capitalize;
          font-family: "Raleway";
          font-style: normal;
          font-weight: 500;
          font-size: 17px;
        }

        .tab-title {
          margin-bottom: 20px;
        }

        .projects-container {
          display: flex;
          gap: 50px;
          margin: 20px 20px 30px 20px;
          flex-direction: row;
          border-radius: 8px;
          box-shadow: 0px 2px 10px rgba(14, 31, 53, 0.08);

          &__image {
            flex: 1;
            img {
              width: 100%;
              height: 100%;
              display: block;
            }
          }

          &__text {
            flex: 1;
            height: inherit;
            display: flex;
            flex-direction: column;
            justify-content: center;

            &__title {
              font-family: "Raleway";
              font-style: normal;
              font-weight: 700;
              font-size: 24px;
              line-height: 31px;
              letter-spacing: 0.005em;
              text-transform: capitalize;
              color: #2d2d2d;
              margin-bottom: 10px;
            }

            &__desc {
              font-family: "Lato";
              font-style: normal;
              font-weight: 400;
              font-size: 16px;
              line-height: 177.18%;
              letter-spacing: 0.01em;
              color: #929292;
              margin-bottom: 20px;
              text-align: justify;
            }

            &__tools {
              display: flex;
              justify-content: space-between;
              align-items: center;
              &__wrapper {
                display: flex;
                gap: 15px;
                img {
                  height: 30px;
                }
              }
            }
          }

          &:nth-child(even) {
            flex-direction: row-reverse;
            .projects-container {
              &__image {
                img {
                  border-top-right-radius: 8px;
                  border-bottom-right-radius: 8px;
                }
              }
              &__text {
                padding: 20px 0 20px 20px;
              }
            }
          }

          &:nth-child(odd) {
            .projects-container {
              &__image {
                img {
                  border-top-left-radius: 8px;
                  border-bottom-left-radius: 8px;
                }
              }
              &__text {
                padding: 20px 20px 20px 0;
              }
            }
          }
        }
      }
    }
  }
}

@media (max-width: $max-width-tablet) {
  .main {
    .section-one {
      &__container {
        padding: 0 20px 0 20px;
        &__wrapper {
          flex-direction: column;
          gap: 10px;
          &__text {
            &__position {
              max-width: 500px;
              margin: 0 auto 20px auto;
              justify-content: center;
              div {
                &:nth-child(1) {
                  display: none;
                }
              }
            }
            &__name {
              font-size: 62px;
              max-width: 500px;
              line-height: 62px;
              text-align: center;
              margin: 0 auto 10px auto;
            }
            &__desc {
              font-size: 15px;
              line-height: 25px;
              max-width: 500px;
              text-align: center;
              margin: 0 auto 10px auto;
            }
            &__touch {
              justify-content: center;
              margin-bottom: 0;
            }
            &__button {
              display: none;
            }
            &__line {
              display: none;
            }
            &__open {
              display: none;
            }
          }
          &__image {
            margin: auto;
            flex-direction: column;
            &__line {
              display: unset;
              background: #6b7280;
              border: 1px solid #e5e7eb;
              width: 100%;
              margin-bottom: 20px;
            }
            &__button {
              display: flex;
              gap: 20px;
              margin-bottom: 20px;
            }
            &__open {
              display: unset;
              font-family: "Inter";
              font-style: normal;
              font-weight: 400;
              font-size: 12px;
              line-height: 16px;
              color: #6b7280;
            }
          }
        }
      }
    }

    .section-two {
      padding: 70px 0 0 0;
      &__container {
        &__title {
          font-size: 38px;
          line-height: 46px;
          margin: 0 auto 20px auto;
        }
        &__tab {
          &__text {
            font-size: 15px;
          }

          .tab-title {
            margin-bottom: 5px;
          }

          .projects-container {
            gap: 30px;

            &__text {
              &__title {
                font-size: 21px;
                line-height: 28px;
                margin-bottom: 5px;
              }
              &__desc {
                font-size: 15px;
                line-height: 150%;
                margin-bottom: 15px;
              }
              &__tools {
                gap: 10px;
                &__wrapper {
                  gap: 8px;
                }
              }
            }
          }
        }
      }
    }
  }
}

@media (max-width: $max-width-mobile) {
  .main {
    .section-one {
      margin-top: 80px;
      &__container {
        &__wrapper {
          gap: 0;
          &__text {
            &__name {
              font-size: 52px;
              line-height: 52px;
            }
            &__desc {
              font-size: 13px;
              line-height: 22px;
              margin: 0 auto 10px auto;
            }
          }
        }
      }
    }

    .section-two {
      margin: 0 auto 70px auto;
      &__container {
        padding: 0;
        &__title {
          font-size: 30px;
          line-height: 38px;
          margin: 0 auto 15px auto;
        }
        &__tab {
          &__text {
            font-size: 14px;
          }

          .tab-title {
            margin-bottom: 0;
          }

          .projects-container {
            gap: 0;
            flex-direction: column;
            margin: 20px;

            &__text {
              &__title {
                font-size: 20px;
                line-height: 26px;
              }
              // &__desc {
              //   font-size: 15px;
              //   line-height: 150%;
              //   margin-bottom: 10px;
              // }
              // &__tools {
              //   flex-direction: column;
              //   align-items: flex-start;
              //   gap: 10px;
              // }
            }

            &:nth-child(even) {
              flex-direction: column;
              .projects-container {
                &__image {
                  img {
                    border-top-right-radius: 8px;
                    border-top-left-radius: 8px;
                    border-bottom-right-radius: 0;
                  }
                }
                &__text {
                  padding: 20px;
                }
              }
            }

            &:nth-child(odd) {
              .projects-container {
                &__image {
                  img {
                    border-top-left-radius: 8px;
                    border-top-right-radius: 8px;
                    border-bottom-left-radius: 0;
                  }
                }
                &__text {
                  padding: 20px;
                }
              }
            }
          }
        }
      }
    }
  }
}
</style>
