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
          title: '三次元視空間内の運動知覚における参照枠',
          abstract: ' 本研究の目的は、三次元空間内での人間の視対象や自己の運動知覚における参照枠を 検討し、その特性を明らかにすることである。視対象や自己の運動知覚における参照枠 を解明することは、三次元空間における自己定位のメカニズムを明らかにすることにつ ながる。さらに、バーチャルリアリティ (VR) システムの応用や航空機,鉄道等の運転 シミュレータ等でしばしば問題となる視覚系、前庭感覚系,触覚系などで処理された情 報間のズレによる不快症状や自己定位のズレなどの不安定性をできるだけ解消するな ど、実場面の問題解決につなげることができる。',
          keyword:  '',
          image: 'https://maedalab-my.sharepoint.com/personal/kuang_longhui_hiel_ist_osaka-u_ac_jp/_layouts/15/download.aspx?share=ESY4oeb7WExEhbnkArEjc8ABIdxoyW9DqRzoLryiP2nhuw',
          link: 'https://maedalab-my.sharepoint.com/:b:/g/personal/kuang_longhui_hiel_ist_osaka-u_ac_jp/ERYmcIihHjFBgNtQX2MExCkBnTGlNq_Hgr-9Q1nXylO_9A?e=7YB5Y0'
        },
        {
          title: 'Visual-Vestibular Interaction: Effects on Self-Motion Perception and Postural Control',
          abstract: "The sensation of self-motion is a common visual illusion which allows inferences concerning visual-vestibular interaction. It may be perceived while gazing at moving clouds, streaming water, or when a train moves on the adjacent track in a railway station. This compelling sensation of body movement can even affect postural balance. On first approaching the problem, a psychologic explanation could be suggested in the sense of Helmholtz’s (1896) Urteilstäuschung. One might assume that these illusions are inferences based upon the conscious or unconscious assumption of a stable environment, so that when the environment does in fact move, the observer infers that he himself is moving. This interpretation would be consistent with the individual’s past experience as the entire visual surround seldom moves uniformly under natural conditions unless the body moves relative to the earth.",
          keyword:  '', 
          image: 'https://maedalab-my.sharepoint.com/personal/kuang_longhui_hiel_ist_osaka-u_ac_jp/_layouts/15/download.aspx?share=ETSkidOKbrpFhwUAgvVevuIBmT7fiuWKQ9KjeKCR7p9crg',
          link: 'https://maedalab-my.sharepoint.com/:b:/g/personal/kuang_longhui_hiel_ist_osaka-u_ac_jp/EeYJb-FJM8FHo4plEHgvL4EBz5QY-mClgFjPVatY7uzMkg?e=SbpYa6'
        },
        {
          title: 'リニアベクション現象を高める広視野空間での周辺視刺激の活用とその効果',
          abstract: 'ベクションとは，視覚刺激を観察することによって発生する運動感覚である．直線方向のベクションをリニアベクション(LV)と呼び，本論文ではこれに着目して周辺視領域との関係について検討を行った．広範な視野領域に視覚刺激を提示するために，全天周型ディスプレイを用いて検討を行った．視覚刺激は先行研究に倣い，ランダムドットとストライプの2種類とした．実験1では視覚刺激提示面の広さがLV の強度に与える影響を確認した．結果として，視覚刺激の提示面が広いほど強いLV が発生することを確認し，水平視野角180度以上の領域もLV の強度に影響を与えることを示唆した．実験2では中心視領域にマスク領域を設けることで，周辺視刺激が引き起こすLV について分析を行った．結果，LV の強度はマスクの大きさが20度のときに最大となり，マスクが80度のときに最小となった．',
          keyword:  '視覚誘導性自己運動感覚，ベクション，周辺視領域，没入型ディスプレイ，マスク領域',
          image: 'https://maedalab-my.sharepoint.com/personal/kuang_longhui_hiel_ist_osaka-u_ac_jp/_layouts/15/download.aspx?share=ETZ0L9jRPSRChv4MRkjdjqYBfyzT2abCRECbYeXyiQGL_A',
          link: 'https://www.rm2c.ise.ritsumei.ac.jp/mclab/pdf/IEICE_j100-d_konishi.pdf'
        },
        {
          title: 'Effects of luminance contrast, averaged luminance and spatial frequency on vection',
          abstract: 'Changing the speed, size and material properties of optic flow can significantly alter the experience of vection (i.e. visually induced illusions of self-motion). Until now, there has not been a systematic investigation of the effects of luminance contrast, averaged luminance and stimulus spatial frequency on vection. This study examined the vection induced by horizontally oriented gratings that continuously drifted downwards at either 20° or 60°/s. Each of the visual motion stimuli tested had one of: (a) six different levels of luminance contrast; (b) four different levels of averaged luminance; and (c) four different spatial frequencies. Our experiments showed that vection could be significantly altered by manipulating each of these visual properties. Vection strength increased with the grating’s luminance contrast (in Experiment 1), its averaged luminance (in Experiment 2), and its spatial frequency (in Experiment 3). Importantly, interactions between these three factors were also found for the vection induced in Experiment 4. While simulations showed that these vection results could have been caused by effects on stimulus motion energy, differences in perceived grating visibility, brightness or speed may have also contributed to our findings.',
          keyword:  '',
          image: 'https://media.springernature.com/lw685/springer-static/image/art%3A10.1007%2Fs00221-021-06214-5/MediaObjects/221_2021_6214_Fig2_HTML.png',
          link: 'https://link.springer.com/article/10.1007/s00221-021-06214-5?fromPaywallRec=false'
        },
        {
          title: 'Future challenges for vection research: definitions, functional significance, measures, and neural bases',
          abstract: 'This paper discusses four major challenges facing modern vection research. Challenge 1 (Defining Vection) outlines the different ways that vection has been defined in the literature and discusses their theoretical and experimental ramifications. The term vection is most often used to refer to visual illusions of self-motion induced in stationary observers (by moving, or simulating the motion of, the surrounding environment). However, vection is increasingly being used to also refer to non-visual illusions of self-motion, visually mediated self-motion perceptions, and even general subjective experiences (i.e., “feelings”) of self-motion. The common thread in all of these definitions is the conscious subjective experience of self-motion. Thus, Challenge 2 (Significance of Vection) tackles the crucial issue of whether such conscious experiences actually serve functional roles during self-motion (e.g., in terms of controlling or guiding the self-motion). After more than 100 years of vection research there has been surprisingly little investigation into its functional significance. Challenge 3 (Vection Measures) discusses the difficulties with existing subjective self-report measures of vection (particularly in the context of contemporary research), and proposes several more objective measures of vection based on recent empirical findings. Finally, Challenge 4 (Neural Basis) reviews the recent neuroimaging literature examining the neural basis of vection and discusses the hurdles still facing these investigations.',
          keyword:  '',
          image: 'https://www.frontiersin.org/files/Articles/129184/fpsyg-06-00193-r2/image_m/fpsyg-06-00193-g002.jpg',
          link: 'https://www.frontiersin.org/journals/psychology/articles/10.3389/fpsyg.2015.00193/full'
        },
        {
          title: 'Second-order motions contribute to vection',
          abstract: "First- and second-order motions differ in their ability to induce motion aftereffects (MAEs) and the kinetic depth effect (KDE). To test whether second-order stimuli support computations relating to motion-in-depth we examined the vection illusion (illusory self motion induced by image flow) using a vection stimulus (V, expanding concentric rings) that depicted a linear path through a circular tunnel. The set of vection stimuli contained differing amounts of first- and second-order motion energy (ME). Subjects reported the duration of the perceived MAEs and the duration of their vection percept. In Experiment 1 both MAEs and vection durations were longest when the first-order (Fourier) components of V were present in the stimulus. In Experiment 2, V was multiplicatively combined with static noise carriers having different check sizes. The amount of first-order ME associated with V increases with check size. MAEs were found to increase with check size but vection durations were unaffected. In general MAEs depend on the amount of first-order ME present in the signal. Vection, on the other hand, appears to depend on a representation of image flow that combines first- and second-order ME.",
          keyword:  'VectionSelf-motionMotion-aftereffectsMotionSecond-order motion', 
          image: 'https://maedalab-my.sharepoint.com/personal/kuang_longhui_hiel_ist_osaka-u_ac_jp/_layouts/15/download.aspx?share=EeWlACtziCFFrBc2WlEOWKYBtljAO87vNqlEMjyBjDTz4A',
          link: 'https://www.sciencedirect.com/science/article/pii/S0042698997004562'
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
        {
          title: 'Effect of Different Display Types on Vection and Its Interaction With Motion Direction and Field Dependence',
          abstract: ' Illusory self-motion (vection) can be generated by visual stimulation. The purpose of the present study was to compare behavioral vection measures including intensity ratings, duration, and onset time across different visual display types. Participants were exposed to a pattern of alternating black-and-white horizontal or vertical bars that moved either in vertical or horizontal direction, respectively. Stimuli were presented on four types of displays in randomized order: (a) large field of view dome projection, (b) combination of three computer screens, (c) single computer screen, (d) large field of view flat projection screen. A Computer Rod and Frame Test was used to measure field dependence, a cognitive style indicating the person’s tendency to rely on external cues (i.e., field dependent) or internal cues (i.e., field independent) with respect to the perception of one’s body position in space. Results revealed that all four displays successfully generated at least moderately strong vection. However, shortest vection onset, longest vection duration, and strongest vection intensity showed for the dome projection and the combination of three screens. This effect was further pronounced in field independent participants, indicating that field dependence can alter vection.',
          keyword:  'Visual perception, Vection, Displays, Frame rate, Rendering, Postural control',
          image: 'https://journals.sagepub.com/cms/10.1177/2041669517707768/asset/images/large/10.1177_2041669517707768-fig2.jpeg',
          link: 'https://journals.sagepub.com/doi/full/10.1177/2041669517707768'
        },
        {
          title: 'Accelerating Self-Motion Displays Produce More Compelling Vection in Depth',
          abstract: 'We examined the vection in depth induced when simulated random self-accelerations (jitter) and periodic self-accelerations (oscillation) were added to radial expanding optic flow (simulating constant-velocity forward self-motion). Contrary to the predictions of sensory-conflict theory frontal-plane jitter and oscillation were both found to significantly decrease the onsets and increase the speeds of vection in depth. Depth jitter and oscillation had lesser, but still significant, effects on the speed of vection in depth. A control experiment demonstrated that adding global perspective motion which simulated a constant-velocity frontal-plane self-motion had no significant effect on vection in depth induced by the radial component of the optic flow. These results are incompatible with the notion that constant-velocity displays produce optimal vection. Rather, they indicate that displays simulating self-acceleration can often produce more compelling experiences of self-motion in depth.',
          keyword:  ' ',
          image: 'https://maedalab-my.sharepoint.com/personal/kuang_longhui_hiel_ist_osaka-u_ac_jp/_layouts/15/download.aspx?share=EWzqUc4YjvhEkR1AEONngs4BiAywtY4ZgZi1_zRp0MAP4Q',
          link: 'https://www.researchgate.net/publication/5453972_Accelerating_Self-Motion_Displays_Produce_More_Compelling_Vection_in_Depth'
        },
        {
          title: 'Independent modulation of motion and vection aftereffects revealed by using coherent oscillation and random jitter in optic flow',
          abstract: 'We added simulated vertical viewpoint jitter and oscillation to radial optic flow displays designed to induce forward vection. Display jitter and oscillation were both found to increase vection strength during, and reduce motion aftereffects (MAE) following, exposure to the optic flow (compared to no-jitter controls). Display jitter, which induced the strongest vection of all the conditions tested, was also found to increase the duration of vection aftereffects (VAE).',
          keyword:  ' ',
          image: 'https://ars.els-cdn.com/content/image/1-s2.0-S0042698911003609-gr1.jpg',
          link: 'https://www.sciencedirect.com/science/article/pii/S0042698911003609?via%3Dihub#f0030'
        },
        {
          title: 'Vection Is Enhanced by Increased Exposure to Optic Flow',
          abstract: 'We examined whether vection strength could be modulated by altering the exposure duration to optic flow. Experiment 1 sourced 150 different video clips from various Japanese animation works which simulated self-motion. Despite large differences in the content of these video clips, we found a significant positive correlation between their play durations and their ratings of vection magnitude. Experiment 2 examined this relationship further using more tightly controlled visual motion stimuli. Vection was induced by presenting the motion of the same expanding grating stimulus for 8, 16, 32, or 64 seconds. While vection onset latencies remained constant across these four conditions, vection magnitude/strength was found to increase systematically with the exposure duration. As predicted by a recent computational model of vection, we conclude that subjective vection strength does depend on the exposure duration to optic flow.',
          keyword:  ' ',
          image: 'https://maedalab-my.sharepoint.com/personal/kuang_longhui_hiel_ist_osaka-u_ac_jp/_layouts/15/download.aspx?share=ESHUj7Fw7yNEmr_keVIQGDABrsa48QqX1edB_f91LVN0Rg',
          link: 'https://journals.sagepub.com/doi/10.1177/2041669518774069'
        },
        {
          title: 'Relationship between vection and motion perception in depth',
          abstract: 'This study examined the effects of cues to motion in depth – namely, stereoscopic (i.e., changing-disparity cues and interocular velocity differences) and changing-size cues on forward and backward vection. We conducted four experiments in which participants viewed expanding or contracting optical flows with the addition of either or both cues. In Experiment 1, participants reported vection by pressing a button whenever they felt it. After each trial, they also rated the magnitude of the vection (from 0 to 100). In Experiments 2 and 3, the participants rated the perceived velocity and motion-in-depth impression of the flows relative to standard stimuli, respectively. In Experiment 4, the participants rated the perceived depth and distance of the display. We observed enhancements in vection, motion-in-depth impression, and perceived depth and distance when either or both types of cues indicated motion-in-depth, as compared to those when the cues did not (Experiments 1, 3, and 4). The perceived velocity changed with cue conditions only for the high velocity condition (Experiment 2). Correlational analyses showed that the vection can be best explained by the motion-in-depth impression. This was partially supported by the multiple regression analyses. These results indicate that the enhancement of vection caused by cues is related to the impression of motion-in-depth rather than the perceived velocity and perceived three-dimensionality.',
          keyword:  ' ',
          image: '//media.springernature.com/full/springer-static/image/art%3A10.3758%2Fs13414-018-1567-y/MediaObjects/13414_2018_1567_Fig4_HTML.png',
          link: 'https://link.springer.com/article/10.3758/s13414-018-1567-y?fromPaywallRec=false'
        },
        {
          title: 'Effects of gaze on vection from jittering, oscillating, and purely radial optic flow',
          abstract: 'In this study, we examined the effects of different gaze types (stationary fixation, directed looking, or gaze shifting) and gaze eccentricities (central or peripheral) on the vection induced by jittering, oscillating, and purely radial optic flow. Contrary to proposals of eccentricity independence for vection (e.g., Post, 1988), we found that peripheral directed looking improved vection and peripheral stationary fixation impaired vection induced by purely radial flow (relative to central gaze). Adding simulated horizontal or vertical viewpoint oscillation to radial flow always improved vection, irrespective of whether instructions were to fixate, or look at, the center or periphery of the self-motion display. However, adding simulated high-frequency horizontal or vertical viewpoint jitter was found to increase vection only when central gaze was maintained. In a second experiment, we showed that alternating gaze between the center and periphery of the display also improved vection (relative to stable central gaze), with greater benefits observed for purely radial flow than for horizontally or vertically oscillating radial flow. These results suggest that retinal slip plays an important role in determining the time course and strength of vection. We conclude that how and where one looks in a self-motion display can significantly alter vection by changing the degree of retinal slip.',
          keyword:  '', 
          image: 'https://maedalab-my.sharepoint.com/personal/kuang_longhui_hiel_ist_osaka-u_ac_jp/_layouts/15/download.aspx?share=EeJPJVak9d9Jj2QhkQZag9UBmxeX0MIjmHoJJJ5Q14QZyw',
          link: 'https://maedalab-my.sharepoint.com/:b:/g/personal/kuang_longhui_hiel_ist_osaka-u_ac_jp/EeYJb-FJM8FHo4plEHgvL4EBz5QY-mClgFjPVatY7uzMkg?e=38Btev'
        },
        {
          title: 'Coherent modulation of stimulus colour can affect visually induced self-motion perception',
          abstract: "The effects of dynamic colour modulation on vection were investigated to examine whether perceived variation of illumination affects self-motion perception. Participants observed expanding optic flow which simulated their forward self-motion. Onset latency, accumulated duration, and estimated magnitude of the self-motion were measured as indices of vection strength. Colour of the dots in the visual stimulus was modulated between white and red (experiment 1), white and grey (experiment 2), and grey and red (experiment 3). The results indicated that coherent colour oscillation in the visual stimulus significantly suppressed the strength of vection, whereas incoherent or static colour modulation did not affect vection. There was no effect of the types of the colour modulation; both achromatic and chromatic modulations turned out to be effective in inhibiting self-motion perception. Moreover, in a situation where the simulated direction of a spotlight was manipulated dynamically, vection strength was also suppressed (experiment 4). These results suggest that observer's perception of illumination is critical for self-motion perception, and rapid variation of perceived illumination would impair the reliabilities of visual information in determining self-motion.",
          keyword:  '', 
          image: 'https://maedalab-my.sharepoint.com/personal/kuang_longhui_hiel_ist_osaka-u_ac_jp/_layouts/15/download.aspx?share=EbKKY1V9KkZMtYZq2fCRg6sBKMwOVLY2QT2W4WUSnuTKpg',
          link: 'https://maedalab-my.sharepoint.com/:b:/g/personal/kuang_longhui_hiel_ist_osaka-u_ac_jp/EbHR3sbNfg9LlllNeupqRpAB0I1vqUDq4Ud9_sJ8lz_tvA?e=aiOCmF'
        },
        {
          title: 'The Oscillating Potential Model of Visually Induced Vection',
          abstract: "Visually induced illusions of self-motion are often referred to as vection. This article developed and tested a model of responding to visually induced vection. We first constructed a mathematical model based on well-documented characteristics of vection and human behavioral responses to this illusion. We then conducted 10,000 virtual trial simulations using this Oscillating Potential Vection Model (OPVM). OPVM was used to generate simulated vection onset, duration, and magnitude responses for each of these trials. Finally, we compared the properties of OPVM’s simulated vection responses with real responses obtained in seven different laboratory-based vection experiments. The OPVM output was found to compare favorably with the empirically obtained vection data.",
          keyword:  'vection, latency, duration, magnitude, index, model', 
          image: 'https://cdn.ncbi.nlm.nih.gov/pmc/blobs/b7f1/5703118/69525ffdf808/10.1177_2041669517742176-fig6.jpg',
          link: 'https://pmc.ncbi.nlm.nih.gov/articles/PMC5703118/'
        },
        {
          title: 'Multisensory Effects on Illusory Self-Motion (Vection): the Role of Visual, Auditory, and Tactile Cues',
          abstract: "A critical component to many immersive experiences in virtual reality (VR) is vection, defined as the illusion of self-motion. Traditionally, vection has been described as a visual phenomenon, but more recent research suggests that vection can be influenced by a variety of senses. The goal of the present study was to investigate the role of multisensory cues on vection by manipulating the availability of visual, auditory, and tactile stimuli in a VR setting. To achieve this, 24 adults ( M age = 25.04) were presented with a rotating stimulus aimed to induce circular vection. All participants completed trials that included a single sensory cue, a combination of two cues, or all three cues presented together. The size of the field of view (FOV) was manipulated across four levels (no-visuals, small, medium, full). Participants rated vection intensity and duration verbally after each trial. Results showed that all three sensory cues induced vection when presented in isolation, with visual cues eliciting the highest intensity and longest duration. The presence of auditory and tactile cues further increased vection intensity and duration compared to conditions where these cues were not presented. These findings support the idea that vection can be induced via multiple types of sensory inputs and can be intensified when multiple sensory inputs are combined.",
          keyword:  ' ', 
          image: 'https://maedalab-my.sharepoint.com/personal/kuang_longhui_hiel_ist_osaka-u_ac_jp/_layouts/15/download.aspx?share=EToY6Qyf9stFrYWXHMIZyBMBxXaH2Rz9V_JH6fIZmU6fMQ',
          link: 'https://www.researchgate.net/publication/353844593_Multisensory_Effects_on_Illusory_Self-Motion_Vection_the_Role_of_Visual_Auditory_and_Tactile_Cues'
        },
        {
          title: 'Vection can be induced in the absence of explicit motion stimuli',
          abstract: "The present study utilized two separate experiments to demonstrate that illusory self-motion (vection) can be induced/modulated by cognition. In the first experiment, two curved lines, which simulated road edges seen while driving at night, were employed. Although the lines induced adequate strength of forward vection, when one of the lines was horizontally reversed, vection was significantly reduced. In the second experiment, two static converging lines with moving characters, which simulated side edges of a straight road with a traffic sign, were utilized. The road sign moved only during the first 5 s. After the sign disappeared, only static lines or a blank screen were able to induce vection. These results suggested that vection was largely affected by cognitive factors and that vection could be induced by implicit motion stimuli.",
          keyword:  ' ', 
          image: 'https://media.springernature.com/full/springer-static/image/art%3A10.1007%2Fs00221-012-3083-y/MediaObjects/221_2012_3083_Fig2_HTML.gif?as=webp',
          link: 'https://link.springer.com/article/10.1007/s00221-012-3083-y'
        },
        {
          title: 'Neural Correlates of Visually Induced Self-Motion Illusion in Depth',
          abstract: " Optic-flow fields can induce the conscious illusion of self-motion in a stationary observer. Here we used functional magnetic resonance imaging to reveal the differential processing of self- and object-motion in the human brain. Subjects were presented a constantly expanding optic-flow stimulus, composed of disparate red–blue dots, viewed through red–blue glasses to generate a vivid percept of three-dimensional motion. We compared the activity obtained during periods of illusory self-motion with periods of object-motion percept. We found that the right MT+, precuneus, as well as areas located bilaterally along the dorsal part of the intraparietal sulcus and along the left posterior intraparietal sulcus were more active during self-motion perception than during object-motion. Additional signal increases were located in the depth of the left superior frontal sulcus, over the ventral part of the left anterior cingulate, in the depth of the right central sulcus and in the caudate nucleus/putamen. We found no significant deactivations associated with self-motion perception. Our results suggest that the illusory percept of self-motion is correlated with the activation of a network of areas, ranging from motion-specific areas to regions involved in visuo-vestibular integration, visual imagery, decision making, and introspection.",
          keyword:  ' ', 
          image: 'https://oup.silverchair-cdn.com/oup/backfile/Content_public/Journal/cercor/18/8/10.1093_cercor_bhm203/2/m_cercorbhm203f02_ht.jpeg?Expires=1734625132&Signature=Fij4pvLTNLJROLBq0Fw7yoZd7im3F8D9cVy-XqcgZDuEVXGYnBGPu9APj0opYxic6tUseFJOYVVcyO660h9Z-WdQtOxhirUtYad~1s3xpzTBHTCEzGRk7ctMdg3IVF7Bz8Ld0xlIOu9AI95Hfy1Y5AnmOXJolqP1hWp86aIaKKs7ElVLpwObPrpKPGNTuM5DHq~elbR2TfkNUilNgBaL7caOFkY3W4ZYcF~PpycKMzyd5hn4pj0SCCSC7ljN~O8LnPFh16FHjsjtonH7x4FrBj3RnPrtNgrXUmBf~fA34ZxYrt07iAD4ouGIPDAUAT6p1FSVOCAnN3qQj7A6oF1itQ__&Key-Pair-Id=APKAIE5G5CRDK6RD3PGA',
          link: 'https://academic.oup.com/cercor/article/18/8/1779/283474?login=true'
        },
        {
          title: 'Neural Correlates of Visual-Motion Perception as Object- or Self-motion',
          abstract: "Both self-motion and objects moving in our visual field generate visual motion by displacing images on the retina. Resolving this ambiguity may seem effortless but large-field visual-motion stimuli can yield perceptual rivalry between the real percept of object-motion and the illusory percept of self-motion (vection). We used functional magnetic resonance imaging to record brain activity in human observers exposed to constant-velocity roll-motion. This stimulus induced responses in areas reaching from calcarine to parieto-occipital and to ventral and lateral temporo-occipital cortex and the anterior insula. During vection, early motion-sensitive visual areas and vestibular parieto-insular cortex deactivated, whereas higher-order parieto- and temporo-occipital areas known to respond to optical flow retained identical activity levels. Within this sustained response, these latter areas displayed transient activations in response to each perceptual switch as identified in event-related analyses. Our results thus show that these areas are responsive to the type of visual motion stimulus and highly sensitive to its perceptual bistability. The only region to be more active during perceived self-motion was in, or close to, the cerebellar nodulus. This activation may correspond to the gain increase of torsional optokinetic nystagmus during vection and/or to changes in sensory processing related to the rotational percept. In conclusion, we identified neural correlates of perceiving self-motion from vision alone, i.e., in the absence of confirmatory vestibular or proprioceptive input. These functional properties preserve the organism's ability to move accurately in its environment by relying on visual cues under conditions when the other spatial senses fail to provide such information.",
          keyword:  ' ', 
          image: 'https://maedalab-my.sharepoint.com/personal/kuang_longhui_hiel_ist_osaka-u_ac_jp/_layouts/15/download.aspx?share=EQQtCOuFAQ9HoNLo0Wv2FKIBy99VBoEXLAye1PY3caiUSw',
          link: 'https://sci-hub.se/10.1006/nimg.2002.1181'
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
