---
# try also 'default' to start simple
theme: default
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
# background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
# use UnoCSS
css: unocss

fonts:
    sans: 'Noto Sans KR'
    serif: "Noto Serif KR"
    mono: "Nanum Gothic Coding"
layout: 'cover'
---
# World of 3D library in Node.js



<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<!-- <div class="abs-br m-6 flex gap-2">
  <button @click="$slidev.nav.openInEditor()" title="Open in Editor" class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon:edit />
  </button>
  <a href="https://github.com/slidevjs/slidev" target="_blank" alt="GitHub"
    class="text-xl icon-btn opacity-50 !border-none !hover:text-white">
    <carbon-logo-github />
  </a>
</div> -->

<!--
The last comment block of each slide will be treated as slide notes. It will be visible and editable in Presenter Mode along with the slide. [Read more in the docs](https://sli.dev/guide/syntax.html#notes)
-->

---
layout: 'default'

---
# Web3D


- 웹에 내장되어 사용자와 상호작용 할 수 있는 3D 콘텐츠 구현에 관련된 모든 기술을 총칭
- 사용자에게 직관적인 인터페이스를 흥미있게 제공
- 웹의 역할이 점점 더 커짐에 따라, 3D 그래픽 요소가 핵심 비지니스 로직이 되기도 한다



---
layout: 'default'
---
# 3D를 웹에서 보여줄 때 필요한 것

<div @click="$slidev.nav.next" grid="~ cols-2 gap-4">
    <div class="img-wrapper">
        <img src="/3d-graphics.png"/>
    </div>
    <div class="items-center flex">
        <ol>
            <li> 3개 축 (Height/Width/Depth)으로 표현되는 공간 좌표</li>
            <li>부피와 질감을 가지는 물체</li>
            <li>사용자의 뷰포트를 나타낼 카메라</li>
            <li>물체에 투사될 빛</li>
        </ol>
    </div>
</div>
<div v-click class="my-8  text-center font-bold text-red-500">
    <h3> 👉 그러나 개발자가 Row하게 컨트롤하기 매우 어려움</h3>
</div>

<style>

</style>

<!-- 3D 그래픽을 웹에서 보여준다는 것은 height/width/depth 세 가지 축을 가진 공간 좌표에서 기하학적 데이터로 3차원적으로 표현한 뒤, 2차원적 결과물로 출력하는 것이다.

이는 WebGL, HTML Canvas, WebGPU를 이용하여 구현 가능하다. 그러나, 이들은 개발자가 그대로 사용하기에는 너무 어렵다보니 이것들을 편하게 사용할 수 있도록 해주는 라이브러리들이 많이 나왔다. 이번 세션에서 이것들을 알아보도록 하자. -->

---

# 브라우저에서 사용할 수 있는 도구들

<div grid="~ cols-2 gap-4">
    <div>
        <ul>
            <li class="strong">WebGL</li>
            <li class="strong">WebGL 2.0</li>
            <li class="strong">WebGPU</li>
        </ul>
    </div>
    <div class="items-center flex">
        <strong>👉 전부 별도의 플러그인 없이 WebAPI로서 제공</strong>
    </div>
</div>


<br/>

|     |  WebGL   | WebGL 2.0  | WebGPU  |
| --- | ---      | ---        | ---     |
|언어 | Javascript | Javascript | Javascript|
| 기반 | 	OpenGL ES 2.0 | OpenGL ES 3.0 | Vulkan, Metal, Direct3D 12 |
|  GPU 사용 | O  | O  | O  |
|  모바일 지원 | O  | O  | X  |
|  출시일 | 2011년 03월  | 2017년 01월  | 2021년 05월  |



<!-- 핵심은 전부 GPU를 사용할 수 있는데, webapi로서 제공된다는걸 언급 -->




<br>
<br>

<!-- ./components/UtillityBar.vue -->
<UtillityBar/>
<!-- Read more about [Why Slidev?](https://sli.dev/guide/why) -->

<!--
You can have `style` tag in markdown to override the style for the current page.
Learn more: https://sli.dev/guide/syntax#embedded-styles
-->

<style>
/* h1 {
  background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 10%, #146b8c 20%);
  background-size: 100%;
  -webkit-background-clip: text;
  -moz-background-clip: text;
  -webkit-text-fill-color: transparent;
  -moz-text-fill-color: transparent;
} */
</style>

<!--
Here is another comment.
-->

---

# Navigation

Hover on the bottom-left corner to see the navigation's controls panel, [learn more](https://sli.dev/guide/navigation.html)

### Keyboard Shortcuts

|     |     |
| --- | --- |
| <kbd>right</kbd> / <kbd>space</kbd>| next animation or slide |
| <kbd>left</kbd>  / <kbd>shift</kbd><kbd>space</kbd> | previous animation or slide |
| <kbd>up</kbd> | previous slide |
| <kbd>down</kbd> | next slide |

<!-- https://sli.dev/guide/animations.html#click-animations -->
<img
  v-click
  class="absolute -bottom-9 -left-7 w-80 opacity-50"
  src="https://sli.dev/assets/arrow-bottom-left.svg"
/>
<p v-after class="absolute bottom-23 left-45 opacity-30 transform -rotate-10">Here!</p>
<!-- ./components/UtillityBar.vue -->
<UtillityBar/>