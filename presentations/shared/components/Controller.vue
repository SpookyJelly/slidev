<script setup lang="ts">
const moveToShowCase = () => {
  window.location.href = "https://spookyjelly.github.io/slidev/";
};
const moveToGithub = () => {
  window.location.href = "https://github.com/SpookyJelly/slidev";
};
</script>
<template>
  <div id="controller">
    <div>
      <svg
        xmlns="http://www.w3.org/2000/svg"
        xmlns:xlink="http://www.w3.org/1999/xlink"
        aria-hidden="true"
        role="img"
        width="2em"
        height="2em"
        preserveAspectRatio="xMidYMid meet"
        viewBox="0 0 24 24"
      >
        <path
          transform="rotate(90) translate(0 -25)"
          fill="currentColor"
          d="m12 15l4-4H8Zm0 7q-2.075 0-3.9-.788q-1.825-.787-3.175-2.137q-1.35-1.35-2.137-3.175Q2 14.075 2 12t.788-3.9q.787-1.825 2.137-3.175q1.35-1.35 3.175-2.138Q9.925 2 12 2t3.9.787q1.825.788 3.175 2.138q1.35 1.35 2.137 3.175Q22 9.925 22 12t-.788 3.9q-.787 1.825-2.137 3.175q-1.35 1.35-3.175 2.137Q14.075 22 12 22Zm0-2q3.35 0 5.675-2.325Q20 15.35 20 12q0-3.35-2.325-5.675Q15.35 4 12 4Q8.65 4 6.325 6.325Q4 8.65 4 12q0 3.35 2.325 5.675Q8.65 20 12 20Zm0-8Z"
        ></path>
      </svg>
    </div>
    <div>
      <svg
        xmlns="http://www.w3.org/2000/svg"
        xmlns:xlink="http://www.w3.org/1999/xlink"
        aria-hidden="true"
        role="img"
        width="1em"
        height="2em"
        preserveAspectRatio="xMidYMid meet"
        viewBox="0 0 20 50"
      >
        <line x1="0" y1="10" x2="0" y2="40" stroke="current"></line>
      </svg>
    </div>
    <div :onclick="moveToGithub" class="clickable-btn">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        xmlns:xlink="http://www.w3.org/1999/xlink"
        aria-hidden="true"
        role="img"
        width="2em"
        height="2em"
        preserveAspectRatio="xMidYMid meet"
        viewBox="0 0 24 24"
      >
        <path
          fill="currentColor"
          d="M10 20v-6h4v6h5v-8h3L12 3L2 12h3v8z"
        ></path>
      </svg>
    </div>
    <div :onclick="moveToShowCase" class="clickable-btn">
      <svg
        xmlns="http://www.w3.org/2000/svg"
        xmlns:xlink="http://www.w3.org/1999/xlink"
        aria-hidden="true"
        role="img"
        width="2em"
        height="2em"
        preserveAspectRatio="xMidYMid meet"
        viewBox="0 0 24 24"
      >
        <path
          fill="currentColor"
          d="M12 2A10 10 0 0 0 2 12c0 4.42 2.87 8.17 6.84 9.5c.5.08.66-.23.66-.5v-1.69c-2.77.6-3.36-1.34-3.36-1.34c-.46-1.16-1.11-1.47-1.11-1.47c-.91-.62.07-.6.07-.6c1 .07 1.53 1.03 1.53 1.03c.87 1.52 2.34 1.07 2.91.83c.09-.65.35-1.09.63-1.34c-2.22-.25-4.55-1.11-4.55-4.92c0-1.11.38-2 1.03-2.71c-.1-.25-.45-1.29.1-2.64c0 0 .84-.27 2.75 1.02c.79-.22 1.65-.33 2.5-.33c.85 0 1.71.11 2.5.33c1.91-1.29 2.75-1.02 2.75-1.02c.55 1.35.2 2.39.1 2.64c.65.71 1.03 1.6 1.03 2.71c0 3.82-2.34 4.66-4.57 4.91c.36.31.69.92.69 1.85V21c0 .27.16.59.67.5C19.14 20.16 22 16.42 22 12A10 10 0 0 0 12 2Z"
        ></path>
      </svg>
    </div>
  </div>
</template>
<style>
#controller {
  position: absolute;
  color: #616161;
  bottom: 10px;
  padding: 10px;
  right: -150px;
  border: solid 1px gold;
  border-top-left-radius: 2rem;
  border-bottom-left-radius: 2rem;
  width: 200px;
  text-align: center;
  transition: all 1s ease-in;
  display: flex;
  gap: 10px;
}

#controller:hover {
  right: -20px;
  transition: all 1s ease-in;
}

.clickable-btn:hover {
  cursor: pointer;
}
</style>
