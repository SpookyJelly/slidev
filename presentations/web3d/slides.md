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
# 3D Graphics in Web



<div class="pt-12">
  <span @click="$slidev.nav.next" class="px-2 py-1 rounded cursor-pointer" hover="bg-white bg-opacity-10">
    Press Space for next page <carbon:arrow-right class="inline"/>
  </span>
</div>

<!-- ./components/UtillityBar.vue -->
<UtillityBar/>

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

<!-- ./components/UtillityBar.vue -->
<UtillityBar/>

---
layout: 'default'
---
# Requirements for rendering 3D on web

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

<!-- ./components/UtillityBar.vue -->
<UtillityBar/>

<style>

</style>

<!-- 3D 그래픽을 웹에서 보여준다는 것은 height/width/depth 세 가지 축을 가진 공간 좌표에서 기하학적 데이터로 3차원적으로 표현한 뒤, 2차원적 결과물로 출력하는 것이다.

이는 WebGL, HTML Canvas, WebGPU를 이용하여 구현 가능하다. 그러나, 이들은 개발자가 그대로 사용하기에는 너무 어렵다보니 이것들을 편하게 사용할 수 있도록 해주는 라이브러리들이 많이 나왔다. 이번 세션에서 이것들을 알아보도록 하자. -->

---

# Tools can be used on web

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



<br>
<br>

<!-- ./components/UtillityBar.vue -->
<UtillityBar/>

<!-- 핵심은 전부 GPU를 사용할 수 있는데, webapi로서 제공된다는걸 언급 -->

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
layout: default
---
# API exists. but....
너무 빡세요


<div class="flex justify-center">
    <div id='img-wrapper'>
        <img src="/lose_your_sanity.png"/>
    </div>
</div>
<h3 class="text-center my-5 text-stroke-sm text-white">When You Opened Webgl2 fundamentals Page</h3>

<!-- ./components/UtillityBar.vue -->
<UtillityBar/>

<style>
    #img-wrapper {
        width:350px    
    }
    #img-wrapper img{
        aspect-ratio: 3/4
    }
    h3{
        width:350px;
        position:fixed;
        top: 90px;
        left: 50%;
        transform: translate(-50%,50%);
        -webkit-text-stroke:1px black;
        font-size: 2rem;
    }
</style>

<!-- API는 존재하지만 상당한 러닝커브가 있음을 어필 -->

---
---
# Frameworks!
프레임워크 전성시대


<div style="width:500px" class="m-auto">
    <img src="/framework_example.png" style="width:100%; height:100%"/>
</div>

<!-- ./components/UtillityBar.vue -->
<UtillityBar/>


<!-- 그래서 JS 생태계에서는 이들을 편하게 쓸 수 해줄 수 있는 프레임워크들이 많이 생겼습니다. 
하지만 대부분의 프로젝트가 오픈소스 였기에, 현재 (2022년)까지 계속 액티브하게 남아있는 프로젝트는 드뭅니다.

3D 그래픽스는 고도로 복잡한 작업이고, 각 프레임워크마다 이를 구현하는 방식과 API는 확연히 다릅니다. 따라서, 장기적으로 진행되어야할 프로젝트라면 단단하고 오래 갈 수 있는 프레임워크를 고르는 것이 중요한 것은 당연합니다
-->
---
---
# Frameworks!
프레임워크 전성시대

<div class="my-10 justify-center flex">
    <p style="font-size:10rem; display:inline-block; align-self:center; line-height:unset;" class="text-center">🤔</p>
</div>
<div v-click class="text-center"> 
    <h3> 프레임워크는 많은데... 그래서 뭘 써야하는거야?</h3>
</div>

<!-- ./components/UtillityBar.vue -->
<UtillityBar/>

<!-- 그래서 살펴보고 몇가지를 골라봤다 -->

---
---
# Criteria
평가 기준

<br/>

<div grid="~ cols-2" class="gap-5">
    <div>
        <h3 class="mb-4">정량지표</h3>
        <hr/>
        <ul class="my-2">
            <li>type defination 제공</li>
            <li>그룹 단위의 Maintainer </li>
            <li>Github Stars</li>
        </ul>
    </div>
    <div>
        <h3 class="mb-4">정성지표</h3>
        <hr/>
        <ul class="my-2">
            <li>커뮤니티 활성도</li>
            <li>개발 자유도</li>
            <li>적은 코드량</li>
            <li>Well-made Docs</li>
        </ul>
    </div>
</div>

<!-- ./components/UtillityBar.vue -->
<UtillityBar/>
<!-- 이 요소들을 만족하는 라이브러리들 소개  원래는 잔뜩 있었는데, 죽어버린 라이브러리들이 너무 많다는 이야기도 언급하면 좋음-->


---
layout: iframe-left
url: https://threejs.org/docs/
---
# Three.js
가장 오래되고 유명한 라이브러리

<br/>
<br/>

**정량지표**

|   |   |
|---|---|
| Type Defination | O |
| 그룹 단위의 Maintainer | X |
| Github Stars | 87,190 (2022/12)|


<!-- ./components/UtillityBar.vue -->
<UtillityBar/>

---
layout: iframe-left
url: https://doc.babylonjs.com/features/introductionToFeatures
---
# Babylon.js
MS에서 개발하는 3D 엔진

<br/>
<br/>

**정량지표**

|   |   |
|---|---|
| Type Defination | Built-in TS |
| 그룹 단위의 Maintainer | O |
| Github Stars | 18,859 (2022/12)|


<!-- ./components/UtillityBar.vue -->
<UtillityBar/>

---
layout: iframe-left
url: https://aframe.io/examples/showcase/helloworld/
---
# A-Frame
WebVR에 특화된 프레임워크

<br/>
<br/>

**정량지표**
|   |   |
|---|---|
| Type Defination | O |
| 그룹 단위의 Maintainer | O |
| Github Stars | 14,804 (2022/12)|


<!-- ./components/UtillityBar.vue -->
<UtillityBar/>

---
---
# I choose..
(통상적인 웹인 경우)

<br/>
<br/>

> #### *Three.js* or *Bablyon.js*

<br/>
<br/>


Because of...

<v-clicks>

- 넓은 생태계
- 광대한 학습자료
- 활발한 개발자들

</v-clicks>

 <!-- ./components/UtillityBar.vue -->
<UtillityBar/>

<!-- 통상적인 웹 환경에서는 사실상 three.js, babylon.js 둘 중 하나 선택임
둘 다 충분한 생태계를 가지고 있고, 관련 자료도 많을 뿐더러, 적극적으로 개발되고 있기 때문
 -->

---
---
# Showcase
직접 테스트 해보세요

<div grid="~ cols-2 gap-4">
    <div>
        <p>Three.js</p>
        <!-- ./components/ThreeExample.vue -->
        <ThreeExample/>
    </div>
    <div>
        <p>Babylon.js</p>
        <!-- ./components/BabylonExample.vue -->
        <BabylonExample/>
    </div>
</div>

<!-- ./components/UtillityBar.vue -->
<UtillityBar/>

---
layout: two-cols

---
<div style="margin-right:20px;">
    <span>Three.js</span>
    
```ts {all|1}
onMounted(() => {
    //...
    /* camera */
    const camera = new THREE.PerspectiveCamera(%opt%)
    /** scene */
    const scene = new THREE.Scene()
    /* light */
    const light = new THREE.PointLight(%opt%)
    scene.add(light) 

    /* object */
    const sphere = new THREE.Mesh(
        // Mesh의 형상을 정의하는 gemetry
        new THREE.SphereGeometry(%opt%), 
        //  Mesh의 색,질감을 정의하는 material
        new THREE.MeshPhongMaterial(%opt%) 
    )
    scene.add(sphere)
    //... object 정의

    const renderer = new THREE.WebGLRenderer();
    // ** camera와 별도로 control를 생성후 부착해야 조작 가능
    const controls = new ArcballControls(
        camera, renderer.domElement
    );
```
</div>

::right::



<div>
<span style="visibility:hidden">. </span>
```ts {all}
    // requestAnimationFrame API를 사용해 직접 renderer 부팅
    const tick = () => {
      renderer.render(scene, camera);
      window.requestAnimationFrame(tick); // <-- must be required
    };
    tick();

})
```

<h3>👉 Result </h3>
    <br/>
    <!-- ./components/ThreeExample.vue -->
    <ThreeExample/>
</div>



<!-- ./components/UtillityBar.vue -->
<UtillityBar/>

<style>
    .slidev-layout .two-columns{
        gap:20px !important
    }
    .col-left{
        padding:100px !important
    }

</style>


---
layout: two-cols 
---

<div style="margin-right:20px;">
    <small>Babylon.js</small>

```ts{2|1|3}
onMounted(()=>{
    //...
    /* Bablyon은 Engine 인스턴스가 선행적으로 요구됨 */
    const engine = new Engine(canvas)
    
    /* camera */
    const camera = new ArcRotateCamera(%opt%)
    // 카메라에 맞는 controller가 생성시점에 같이 생성
    camera.attachControl(canvas)
    
    //* light */
    const light = new HemisphericLight(%opt%, scene);
    
    //* object*/
    const sphere = CreateSphere(%opt%)
    const material = new GridMaterial(%opt)
    sphere.material = material
    //... object 정의

    engine.runRenderLoop(() => {
        scene.render()
    })
    
})
```
</div>

::right::

<div>
    <h3>👉 Result </h3>
    <br/>
    <!-- ./components/BabylonExample.vue -->
    <BabylonExample/>
</div>

<!-- ./components/UtillityBar.vue -->
<UtillityBar/>

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
