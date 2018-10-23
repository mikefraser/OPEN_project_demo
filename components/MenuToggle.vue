<template>
	<button class="tgl" :aria-pressed="menuActive" @click="toggleMenuActive">
		<svg class="tgl_ic" viewBox="0 -3 24 23">
				<path class="line_1" d="M23,0 q1,0 1,1 v1 q0,1 -1,1 h-22 q-1,0 -1,-1 v-1 q0,-1 1,-1 Z"/>
				<path class="line_2" d="M23,7 q1,0 1,1 v1 q0,1 -1,1 h-22 q-1,0 -1,-1 v-1 q0,-1 1,-1 Z"/>
				<path class="line_3" d="M23,14 q1,0 1,1 v1 q0,1 -1,1 h-22 q-1,0 -1,-1 v-1 q0,-1 1,-1 Z"/>
		</svg>
		<span class="tgl_txt">Open / Close Menu</span>
	</button>
</template>

<script>
export default {
  data: function() {
    return {
      menuActive: false
    };
  },
  methods: {
    toggleMenuActive: function() {
      this.menuActive = !this.menuActive;
    }
  }
};
</script>

<style lang="scss" scoped>
// ---- Vars ----
$br: 0.25em;
$color1: $highlight_lite;
$color2: $head_txt_col;
$color3: $highlight_col;

%clear_btn_styles {
  background: none;
  border: none;
  outline: none;
  padding: 0;
  cursor: pointer;
  color: currentcolor;
}
%visually_hidden {
  position: absolute;
  clip: rect(1px, 1px, 1px, 1px);
  padding: 0;
  border: 0;
  height: 1px;
  width: 1px;
  overflow: hidden;
}

button {
  position: relative;
  border-radius: $br/2;
  z-index: 1;
}

.tgl {
  @extend %clear_btn_styles;
  display: block;
  width: 1.5em;

  &_txt {
    @extend %visually_hidden;
  }

  &_ic {
    // height: 4em;
    // padding: 0.75em;
    // opacity: 0.5;
    // transition: 0.3s ease-in-out opacity;
    // will-change: opacity;
    // border: 0.1px solid red;

    [class^="line"] {
      fill: $color1;
      will-change: transform, fill;
      animation-duration: 0.4s;
      animation-timing-function: ease-in-out;
      animation-fill-mode: forwards;
    }
    [class*="_1"] {
      transform-origin: 11px 2px;
    }
    [class*="_2"] {
      transform-origin: 12px 11px;
    }
    [class*="_3"] {
      transform-origin: 11px 15px;
    }

    &:hover [class^="line"],
    &:focus [class^="line"] {
      fill: $color3;
    }
  }

  // If False  &[aria-pressed="false"]
  [class*="_1"] {
    animation-name: bar1toOpen;
  }
  [class*="_2"] {
    animation-name: bar2toOpen;
  }
  [class*="_3"] {
    animation-name: bar3toOpen;
  }
  //
  &[aria-pressed="true"] {
    [class*="_1"] {
      animation-name: bar1toClose;
    }
    [class*="_2"] {
      animation-name: bar2toClose;
    }
    [class*="_3"] {
      animation-name: bar3toClose;
    }
  }
}

// Animations
//--------------------

@keyframes bar1toClose {
  50% {
    transform: translatey(6px);
  }
  100% {
    transform: translatey(6px) rotate(45deg);
    fill: $color2;
  }
}
@keyframes bar2toClose {
  //   50% {
  //     transform: rotate(0);
  //   }
  100% {
    // transform: rotate(45deg);
    // fill: $color2;
    opacity: 0;
  }
}
@keyframes bar3toClose {
  50% {
    transform: translatey(-6px);
  }
  100% {
    transform: translatey(-6px) rotate(-45deg);
    fill: $color2;
  }
}
@keyframes bar1toOpen {
  0% {
    transform: translatey(6px) rotate(45deg);
    fill: $color2;
  }
  50% {
    transform: translatey(6px);
  }
}
@keyframes bar2toOpen {
  0% {
    // transform: rotate(45deg);
    // fill: $color2;
    opacity: 0;
  }
  //   50% {
  //     transform: rotate(0);
  //   }
}
@keyframes bar3toOpen {
  0% {
    transform: translatey(-6px) rotate(-45deg);
    fill: $color2;
  }
  50% {
    transform: translatey(-6px);
  }
}
</style>

