<template>
  <section>
    <div class="scroll-content">
      <div class="scroll" data-scroll>
        <div class="scroll-content" data-scroll-content>
          <article class="slide slide--1 js-slide">
            <div class="slide__inner">
              <div class="slide__img js-transition-img">
                <figure class="js-transition-img__inner">
                  <img src="~/assets/cover/Screenshot-279.jpg">
                </figure>
              </div>
            </div>
          </article>

          <article class="slide slide--2 js-slide">
            <div class="slide__inner">
              <div class="slide__img js-transition-img">
                <figure class="js-transition-img__inner">
                  <img src="~/assets/cover/Screenshot-286.jpg">
                </figure>
              </div>
            </div>
          </article>

          <article class="slide slide--3 js-slide">
            <div class="slide__inner">
              <div class="slide__img">
                <figure>
                  <img src="~/assets/cover/iuygtfd-3.jpg">
                </figure>
              </div>
            </div>
          </article>

          <article class="slide slide--1 js-slide">
            <div class="slide__inner">
              <div class="slide__img">
                <figure>
                  <img src="~/assets/cover/Screenshot-293.jpg">
                </figure>
              </div>
            </div>
          </article>

          <article class="slide slide--2 js-slide">
            <div class="slide__inner">
              <div class="slide__img">
                <figure>
                  <img src="~/assets/cover/465413.jpg">
                </figure>
              </div>
            </div>
          </article>

          <article class="slide slide--3 js-slide">
            <div class="slide__inner">
              <div class="slide__img">
                <figure>
                  <img src="~/assets/cover/006-3-5b0309b942396.jpg">
                </figure>
              </div>
            </div>
          </article>

          <article class="slide slide--1 js-slide">
            <div class="slide__inner">
              <div class="slide__img js-transition-img">
                <figure class="js-transition-img__inner">
                  <img src="~/assets/cover/002-12435465678o.jpg">
                </figure>
              </div>
            </div>
          </article>

          <article class="slide slide--2 js-slide">
            <div class="slide__inner">
              <div class="slide__img js-transition-img">
                <figure class="js-transition-img__inner">
                  <img src="~/assets/cover/Screenshot-388.jpg">
                </figure>
              </div>
            </div>
          </article>

          <article class="slide slide--3 js-slide">
            <div class="slide__inner">
              <div class="slide__img">
                <figure>
                  <img src="~/assets/cover/006-1-5afc40baca5da.jpg">
                </figure>
              </div>
            </div>
          </article>
        </div>

        <div class="scroll-content scroll-content--last" data-scroll-content>
          <article class="slide slide--1 js-slide">
            <div class="slide__inner">
              <div class="slide__sub-title">
                <h1>8Ball – 你抓不到我</h1>
              </div>
              <!-- <h1 class="slide__title">
                <div class="js-transition-title"></div>
              </h1>-->
              <div class="slide__img slide__img--proxy"></div>
            </div>
          </article>

          <article class="slide slide--2 js-slide">
            <div class="slide__inner">
              <div class="slide__sub-title">
                <h1>LC - I GOT DIS</h1>
              </div>
              <div class="slide__img slide__img--proxy"></div>
            </div>
          </article>

          <article class="slide slide--3 js-slide">
            <div class="slide__inner">
              <div class="slide__sub-title">
                <h1>頑童MJ116 【走跳】</h1>
              </div>
              <div class="slide__img slide__img--proxy"></div>
            </div>
          </article>

          <article class="slide slide--1 js-slide">
            <div class="slide__inner">
              <div class="slide__sub-title">
                <h1>RACO G 雞腿飯 – TAIPEI FREESTYLE</h1>
              </div>
              <div class="slide__img slide__img--proxy"></div>
            </div>
          </article>

          <article class="slide slide--2 js-slide">
            <div class="slide__inner">
              <div class="slide__sub-title">
                <h1>Ty. ft. Higher Brothers – 功成名就</h1>
              </div>
              <div class="slide__img slide__img--proxy"></div>
            </div>
          </article>

          <article class="slide slide--3 js-slide">
            <div class="slide__inner">
              <div class="slide__sub-title">
                <h1>PRETTYNICE LTD. 3030 360° VR Lookbook</h1>
              </div>
              <div class="slide__img slide__img--proxy"></div>
            </div>
          </article>

          <article class="slide slide--1 js-slide">
            <div class="slide__inner">
              <div class="slide__sub-title">
                <h1>頑童MJ116 【幹大事 BIG THING】</h1>
              </div>
              <div class="slide__img slide__img--proxy"></div>
            </div>
          </article>

          <article class="slide slide--2 js-slide">
            <div class="slide__inner">
              <div class="slide__sub-title">
                <h1>頑童MJ116 【辣台妹 HOT CHICK】</h1>
              </div>
              <div class="slide__img slide__img--proxy"></div>
            </div>
          </article>

          <article class="slide slide--3 js-slide">
            <div class="slide__inner">
              <div class="slide__sub-title">
                <h1>Ty. ft.謝帝 BO$$ X – 『母老虎』</h1>
              </div>
              <div class="slide__img slide__img--proxy"></div>
            </div>
          </article>
        </div>

        <div class="scrollbar" data-scrollbar>
          <div class="scrollbar__handle js-scrollbar__handle"></div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  mounted() {
    const math = {
      lerp: (a, b, n) => {
        return (1 - n) * a + n * b
      },
      norm: (value, min, max) => {
        return (value - min) / (max - min)
      }
    }

    const config = {
      height: window.innerHeight,
      width: window.innerWidth
    }

    class Smooth {
      constructor() {
        this.bindAll()

        this.el = document.querySelector('[data-scroll]')
        this.content = [...document.querySelectorAll('[data-scroll-content]')]

        this.dom = {
          el: this.el,
          content: this.content,
          elems: [
            [...this.content[0].querySelectorAll('.js-slide')],
            [...this.content[1].querySelectorAll('.js-slide')]
          ],
          handle: this.el.querySelector('.js-scrollbar__handle')
        }

        this.data = {
          total: this.dom.elems[0].length - 1,
          current: 0,
          last: {
            one: 0,
            two: 0
          },
          on: 0,
          off: 0
        }

        this.bounds = {
          elem: 0,
          content: 0,
          width: 0,
          max: 0,
          min: 0
        }

        this.rAF = null
        this.parallax = null

        this.init()
      }

      bindAll() {
        ;['scroll', 'run', 'resize'].forEach(
          fn => (this[fn] = this[fn].bind(this))
        )
      }

      setStyles() {
        this.dom.el.style.position = 'fixed'
        this.dom.el.style.top = 0
        this.dom.el.style.left = 0
        this.dom.el.style.height = '100%'
        this.dom.el.style.width = '100%'
        this.dom.el.style.overflow = 'hidden'
      }

      setBounds(elems) {
        let w = 0

        elems.forEach((el, index) => {
          const bounds = el.getBoundingClientRect()

          el.style.position = 'absolute'
          el.style.top = 0
          el.style.left = `${w}px`

          w = w + 50 + bounds.width

          this.bounds.width = w - 156
          this.bounds.max = this.bounds.width - config.width

          console.log(this.bounds.width, this.bounds.max)

          if (this.data.total === index && elems === this.dom.elems[0]) {
            this.dom.content[0].style.width = `${w}px`
            this.dom.content[1].style.width = `${w}px`
            document.body.style.height = `${w}px`
          }
        })
      }

      resize() {
        this.setBounds(this.dom.elems[0])
        this.setBounds(this.dom.elems[1])
        this.scroll()
      }

      preload() {
        this.setBounds(this.dom.elems[0])
        this.setBounds(this.dom.elems[1])
      }

      scroll() {
        this.data.current = window.scrollY
        this.clamp()
      }

      clamp() {
        this.data.current = Math.min(
          Math.max(this.data.current, 0),
          this.bounds.max
        )
      }

      run() {
        this.data.last.one = math.lerp(
          this.data.last.one,
          this.data.current,
          0.085
        )
        this.data.last.one = Math.floor(this.data.last.one * 100) / 100

        this.data.last.two = math.lerp(
          this.data.last.two,
          this.data.current,
          0.08
        )
        this.data.last.two = Math.floor(this.data.last.two * 100) / 100

        const diff = this.data.current - this.data.last.one
        const acc = diff / config.width
        const velo = +acc
        const bounce = 1 - Math.abs(velo * 0.25)
        const skew = velo * 7.5

        this.dom.content[0].style.transform = `translate3d(-${this.data.last.one.toFixed(
          2
        )}px, 0, 0) scaleY(${bounce}) skewX(${skew}deg)`
        this.dom.content[1].style.transform = `translate3d(-${this.data.last.two.toFixed(
          2
        )}px, 0, 0) scaleY(${bounce})`

        const scale = math.norm(this.data.last.two, 0, this.bounds.max)

        this.dom.handle.style.transform = `scaleX(${scale})`

        this.requestAnimationFrame()
      }

      on() {
        this.setStyles()
        this.setBounds(this.dom.elems[0])
        this.setBounds(this.dom.elems[1])
        this.addEvents()

        this.requestAnimationFrame()
      }

      requestAnimationFrame() {
        this.rAF = requestAnimationFrame(this.run)
      }

      resize() {
        this.setBounds()
      }

      addEvents() {
        window.addEventListener('scroll', this.scroll, { passive: true })
      }

      init() {
        this.preload()
        this.on()
      }
    }
    // Init classes
    const smooth = new Smooth()
  }
}
</script>

<style>
body {
  overflow-y: scroll;
  background-color: #000;
  user-select: none;
}
h1,
h2 {
  font-weight: normal;
}
figure {
  padding: 0;
  margin: 0;
}
@media screen and (min-width: 1024px) {
  .scroll-content {
    display: flex;
    white-space: nowrap;
    position: relative;
    height: 100vh;
  }
  .scroll-content--last {
    position: absolute;
    top: 0;
    left: 0;
  }

  .slide {
    display: flex;
    width: 50vw;
    height: 100%;
    padding: 25vh 0 10vh 0;
  }
  .slide--1 {
    align-items: flex-start;
  }
  .slide--2 {
    align-items: flex-end;
  }
  .slide--3 {
    align-items: center;
  }
  .slide:last-child {
    width: 65vw;
    padding-right: 15vw;
  }
  .slide__inner {
    position: relative;
    padding-left: 15vw;
    width: 100%;
  }
  .slide__sub-title {
    position: absolute;
    top: 15%;
    left: 5vw;
    color: rgba(255, 255, 255, 0.5);
    font-size: 1vw;
  }
  .slide__title {
    position: absolute;
    top: 20.5%;
    left: 7.5vw;
    color: #fff;
    font-size: 4vw;
    z-index: 2;
    overflow: hidden;
  }
  .slide__project {
    color: #fff;
    position: absolute;
    top: 100%;
    right: 5%;
    font-size: 1.15vw;
    padding-top: 1.5vw;
  }
  .slide__img {
    position: relative;
    overflow: hidden;
    padding-top: 65%;
    width: 100%;
  }
  .slide__img figure {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
  }
  .slide__img figure img {
    position: absolute;
    top: 0;
    left: 0;
    /* height: 100%; */
    width: 100%;
    -o-object-fit: cover;
    object-fit: cover;
  }

  img {
    display: block;
    width: 100%;
    height: auto;
  }

  .scrollbar {
    position: absolute;
    bottom: 7.5%;
    left: 20%;
    right: 20%;
    height: 1px;
    background-color: rgba(255, 255, 255, 0.25);
  }
  .scrollbar__handle {
    position: absolute;
    top: 0;
    left: 0;
    width: 100%;
    height: 100%;
    transform: scaleX(0);
    transform-origin: left;
    background-color: #fff;
  }
}
</style>
