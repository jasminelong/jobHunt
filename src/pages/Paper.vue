<template>
  <v-container fluid>
    <v-row>
      <!-- 使用 v-for 循环遍历数组，渲染多个卡片 -->
      <v-col
        v-for="(paper, index) in paperes"
        :key="index"
        cols="12"
      >
        <v-card class="d-flex flex-row mx-auto my-4">
          <!-- 图片部分，位于左侧，调整宽度和高度以使图片更大 -->
          <v-img
            :src="paper.image"
            height="300"
            width="300"
            class="ma-3"
          ></v-img>
          <!-- 文字内容部分，位于右侧 -->
          <v-card-text class="d-flex flex-column justify-center">
            <v-card-title class="wrap-text custom-title-color">{{ paper.title }}</v-card-title>
            <div>{{ paper.abstract }}</div>
            <div class="keyword-chip">{{ paper.keyword }}</div>
            <v-card-actions class="mt-4"  >
              <v-btn class="click-button" color="orange" @click="navigateTo(paper.link)">click</v-btn>
            </v-card-actions>
          </v-card-text>
          
        </v-card>
      </v-col>
    </v-row>
  </v-container>
</template>

<script>
export default {
  data() {
    return {
      // 定义一个数组来存储卡片的相关数据
      paperes: [
      {
          title: 'Measuring vection: a review and critical evaluation of different methods for quantifying illusory self-motion',
          abstract: 'The sensation of self-motion in the absence of physical motion, known as vection, has been scientifically investigated for over a century. As objective measures of, or physiological correlates to, vection have yet to emerge, researchers have typically employed a variety of subjective methods to quantify the phenomenon of vection. These measures can be broadly categorized into the occurrence of vection (e.g., binary choice yes/no), temporal characteristics of vection (e.g., onset time/latency, duration), the quality of the vection experience (e.g., intensity rating scales, magnitude estimation), or indirect (e.g., distance travelled) measures. The present review provides an overview and critical evaluation of the most utilized vection measures to date and assesses their respective merit. Furthermore, recommendations for the selection of the most appropriate vection measures will be provided to assist with the process of vection research and to help improve the comparability of research findings across different vection studies.',
          keyword:  '',
          image: 'https://media.springernature.com/full/springer-static/image/art%3A10.3758%2Fs13428-023-02148-8/MediaObjects/13428_2023_2148_Fig1_HTML.png?as=webp',
          link: 'https://link.springer.com/article/10.3758/s13428-023-02148-8'
        },
        {
          title: 'Effects of luminance contrast, averaged luminance and spatial frequency on vection',
          abstract: 'Changing the speed, size and material properties of optic flow can significantly alter the experience of vection (i.e. visually induced illusions of self-motion). Until now, there has not been a systematic investigation of the effects of luminance contrast, averaged luminance and stimulus spatial frequency on vection. This study examined the vection induced by horizontally oriented gratings that continuously drifted downwards at either 20° or 60°/s. Each of the visual motion stimuli tested had one of: (a) six different levels of luminance contrast; (b) four different levels of averaged luminance; and (c) four different spatial frequencies. Our experiments showed that vection could be significantly altered by manipulating each of these visual properties. Vection strength increased with the grating’s luminance contrast (in Experiment 1), its averaged luminance (in Experiment 2), and its spatial frequency (in Experiment 3). Importantly, interactions between these three factors were also found for the vection induced in Experiment 4. While simulations showed that these vection results could have been caused by effects on stimulus motion energy, differences in perceived grating visibility, brightness or speed may have also contributed to our findings.',
          keyword:  '',
          image: 'https://media.springernature.com/lw685/springer-static/image/art%3A10.1007%2Fs00221-021-06214-5/MediaObjects/221_2021_6214_Fig2_HTML.png',
          link: 'https://link.springer.com/article/10.1007/s00221-021-06214-5?fromPaywallRec=false'
        },
        {
          title: 'Measuring circular vection speed in a virtual reality headset',
          abstract: 'Understanding the relationship between vection speed and display speed is important to help ensure accurate self-motion experiences in a variety of applications. In the present research, a virtual optokinetic drum was used to induce circular vection at three distinct constant velocities and a method for measuring circular vection speed was developed and examined. In Experiment 1, vection strength was measured using a traditional magnitude estimation rating technique. An optokinetic drum presented on a virtual reality (VR) headset rotated in the yaw axis at slow, medium, and fast speeds. Magnitude estimation ratings were greatest during the fast condition in Experiment 1, replicating previous findings and validating the use of the virtual optokinetic drum in a VR headset. In Experiment 2, participants spun a circular knob in a clockwise or counter-clockwise direction to index their vection speed, direction and duration. The speed at which participants spun the knob increased with drum speed. Vection speed was much faster than the optokinetic drum’s speed, demonstrating that participants may perceive self-motion at faster speeds than intended. It is recommended that indices of vection speed such as the circular knob be used to better understand the relationship between graphic speed and vection speed.',
          keyword:  'VR headset, vection speed, The trial ended with the appearance of a grey screen',
          image: 'https://ars.els-cdn.com/content/image/1-s2.0-S0141938221000603-gr2.jpg',
          link: 'https://www.sciencedirect.com/science/article/pii/S0141938221000603?via%3Dihub'
        },
        {
          title: 'Effects of gaze on vection from jittering, oscillating, and purely radial optic flow',
          abstract: 'In this study, we examined the effects of different gaze types (stationary fixation, directed looking, or gaze shifting) and gaze eccentricities (central or peripheral) on the vection induced by jittering, oscillating, and purely radial optic flow. Contrary to proposals of eccentricity independence for vection (e.g., Post, 1988), we found that peripheral directed looking improved vection and peripheral stationary fixation impaired vection induced by purely radial flow (relative to central gaze). Adding simulated horizontal or vertical viewpoint oscillation to radial flow always improved vection, irrespective of whether instructions were to fixate, or look at, the center or periphery of the self-motion display. However, adding simulated high-frequency horizontal or vertical viewpoint jitter was found to increase vection only when central gaze was maintained. In a second experiment, we showed that alternating gaze between the center and periphery of the display also improved vection (relative to stable central gaze), with greater benefits observed for purely radial flow than for horizontally or vertically oscillating radial flow. These results suggest that retinal slip plays an important role in determining the time course and strength of vection. We conclude that how and where one looks in a self-motion display can significantly alter vection by changing the degree of retinal slip.',
          keyword:  'central gaze, radial flow',
          image: ' ',
          link: 'https://link.springer.com/article/10.3758/APP.71.8.1842'
        },
        {
          title: 'Limits of subjective and objective vection for ultra-high frame rate visual displays',
          abstract: 'Large-field optic flow generates the illusory percept of self-motion, termed ‘vection’. Smoother visual motion displays generate a more compelling subjective sense of vection and objective postural responses, as well as a greater sense of immersiveness for the user observing the visual display. Research suggests that the function linking frame rate and vection asymptotes at 60 frames per second (FPS), but previous studies have used only moderate frame rates that do not approach the limits of human perception. Here, we measure vection using subjective and objective (mean frequency and path length of postural centre-of-pressure (COP) excursions) responses following the presentation of high-contrast optic flow stimuli at slow and fast speeds and low and ultra-high frame rates. We achieve this using a novel rendering method implemented with a projector capable of sub-millisecond temporal resolution in order to simulate refresh rates ranging from very low (15 FPS) to ultra-high frame rates (480 FPS). The results suggest that subjective vection was experienced most strongly at 60 FPS. Below and above 60 FPS, subjective vection is generally weaker, shorter, and starts later, although this pattern varied slightly according to the speed of stimuli. For objective measures, while the frequency of postural sway was unaffected by frame rate, COP path length was greatest for 480 FPS stimuli. Together, our results support diminishing returns for vection above 60 FPS and provide insight into the use of high frame rate for enhancing the user experience in visual displays.',
          keyword:  'Visual perception, Vection, Displays, Frame rate, Rendering, Postural control',
          image: 'https://ars.els-cdn.com/content/image/1-s2.0-S014193822030038X-gr1.jpg',
          link: 'https://www.sciencedirect.com/science/article/pii/S014193822030038X?via%3Dihub'
        },
      ],
    };
  },
  methods: {
    // 定义导航方法，跳转到外部链接
    navigateTo(link) {
      window.open(link, '_blank');// 跳转到指定的URL
    },
  },
};
</script>

<style scoped>
.v-card-title {
  padding: 0.5rem 0rem;
}
.keyword-chip {
  margin-top: 10px;
  color: #ff8c42; /* 浅橙色，保持风格一致 */
  font-weight: bold;
  margin-right: 8px;
}
.wrap-text {
  white-space: normal; /* 允许文本换行 */
  word-break: break-word; /* 如果需要的话，可以在单词内换行 */
}
.custom-title-color {
  color: #ff5733; /* 修改标题颜色，例如橙红色 */
}
.click-button {
  background-color: #493e37; /* 浅橙色背景，与其他部分相协调 */
  margin-left: -8px;
}
</style>
