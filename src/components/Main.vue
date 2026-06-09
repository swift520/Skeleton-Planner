<script setup>

function restartCaveVideos() {
  const caveVideos = document.querySelectorAll("video[data-key*='cave']");
  caveVideos.forEach(video => {
    video.currentTime = 0;
    video.play();
  });
}

function restartMazeVideos() {
  const mazeVideos = document.querySelectorAll("video[data-key*='maze']");
  mazeVideos.forEach(video => {
    video.currentTime = 0;
    video.play();
  });
}

function restartRealVideos() {
  const realVideos = document.querySelectorAll("video[data-key*='real']");
  realVideos.forEach(video => {
    video.currentTime = 0;
    video.play();
  });
}

</script>


<template>
  <div style="height: 48px;"></div>
    <el-row justify="center" style="margin-bottom: 36px;">
      <el-col :xs="24" :sm="22" :md="22" :lg="20" :xl="16">
        <h1 class="section-title" style="margin-bottom: 28px;">Skeleton-Guided Mapless Navigation via Neural Scene Reconstruction for Dynamic Unstructured Environments</h1>
      </el-col>
    </el-row>

  <div>
    <!-- <el-divider /> -->
    <el-row justify="center" style="margin-bottom: 36px;">
        <el-col :xs="24" :sm="20" :md="20" :lg="17" :xl="14">
            <!-- <h1 style="margin-bottom: 20px;">摘要</h1> -->
            <img src="/public/framework.png" alt="Logo" style="width:100%;margin-bottom:12px;border-radius:10px;" />
            <p style="margin-bottom: 16px;">
                Perception and planning in complex, dynamic, and unstructured environments remain critical bottlenecks for achieving robust and high-precision autonomous navigation of mobile robots.
                This paper proposes a two-stage framework that integrates learning-based environment reconstruction with skeleton-guided path planning. 
                In the front end, a lightweight perception network captures real-time environmental dynamics and estimates occupancy states in occluded regions. 
                An explicit memory module leverages the translation equivariance of convolutional networks to effectively mitigate observational blind spots and long-term memory drift. 
                In the back end, the predicted free space is abstracted into a sparse topological skeleton graph that extracts structurally invariant environmental features. 
                Serving as a compact, high-level representation that fully preserves spatial connectivity, this graph enables efficient reachability analysis and trajectory optimization with strong adaptability to obstacles of different scales. 
                Extensive experiments demonstrate that the proposed method effectively resists dynamic disturbances and maintains stable, globally consistent navigation performance.
            </p>
        </el-col>
    </el-row>
  </div>

  <div>
    <el-divider />

    <el-row justify="center">
      <h2 class="section-title" style="margin-bottom: 12px;">Dynamic Simulation Visualization</h2>
    </el-row>

    <el-row justify="center" style="margin-bottom: 36px;">
      <el-col :xs="24" :sm="22" :md="20" :lg="20" :xl="18">
        <p style="margin-bottom: 24px;">
          Experiments were conducted in two static scene configurations containing dynamic cylindrical obstacles. The maximum speed of the robot was set to 3 m/s, while the velocity of the dynamic obstacles was limited to 1 m/s. The effective detection range of the simulated LiDAR was 10 m, and the BEV projection covered an area of 6.4 m × 6.4 m.
        </p>
        <p style="margin-bottom: 12px;">
          (1) Cave-Like Scenario: Irregular clustered structures generated from a 2D Perlin noise field.
        </p>

        <el-row justify="center" gutter="10">
          <el-col :xs="24" :sm="8" :md="8" :lg="8" :xl="8" style="display:flex;justify-content:center;">
            <div style="display:flex;flex-direction:column;align-items:center;width:100%;">
              <p class="p0"> Roughness 0.5 & Filling Rate 0.25 </p>
              <video key='cave1' data-key='cave1' autoplay loop muted preload playsinline style="width:100%;max-width:550px;aspect-ratio:33/28;border-radius:0px;object-fit:cover;" controlslist="nodownload nofullscreen noremoteplayback noaudio noplaybackrate">
                <source src="/video/cave1.mp4" type="video/mp4">
              </video>
            </div>
          </el-col>
          <el-col :xs="24" :sm="8" :md="8" :lg="8" :xl="8" style="display:flex;justify-content:center;">
            <div style="display:flex;flex-direction:column;align-items:center;width:100%;">
              <p class="p0"> Roughness 0.4 & Filling Rate 0.275 </p>
              <video key='cave2' data-key='cave2' autoplay loop muted preload playsinline style="width:100%;max-width:550px;aspect-ratio:33/28;border-radius:0px;object-fit:cover;" controlslist="nodownload nofullscreen noremoteplayback noaudio noplaybackrate">
                <source src="/video/cave2.mp4" type="video/mp4">
              </video>
            </div>
          </el-col>
          <el-col :xs="24" :sm="8" :md="8" :lg="8" :xl="8" style="display:flex;justify-content:center;">
            <div style="display:flex;flex-direction:column;align-items:center;width:100%;">
              <p class="p0"> Roughness 0.3 & Filling Rate 0.3 </p>
              <video key='cave3' data-key='cave3' autoplay loop muted preload playsinline style="width:100%;max-width:550px;aspect-ratio:33/28;border-radius:0px;object-fit:cover;" controlslist="nodownload nofullscreen noremoteplayback noaudio noplaybackrate">
                <source src="/video/cave3.mp4" type="video/mp4">
              </video>
            </div>
          </el-col>
        </el-row>
        <div style="height: 6px;"></div>
        <el-row >
          <p class="p0">
          * The video is played at 1.3× playback speed. It shows a composite visualization including: (i) the BEV projection, static occupancy map, and dynamic obstacle motion predictions produced by the perception network (top-left); (ii) the globally fused static occupancy map (bottom-left); and (iii) the simulation environment, sparse skeleton graph, and planned trajectory (right).
          </p>
        </el-row>
        <el-row justify="center">
          <el-button type="primary" @click="restartCaveVideos" class="custom-button">Restart Videos</el-button>
        </el-row>
        
      </el-col>
    </el-row>
  </div>
  <div>
    <el-row justify="center" style="margin-bottom: 6px;">
      <el-col :xs="24" :sm="22" :md="20" :lg="20" :xl="18">
        <p style="margin-bottom: 12px;">
          (2) Maze-Like Scenario: Connected walls with randomly varying thickness are arranged on a 9 × 14 grid.
        </p>
                <el-row justify="center" gutter="10">
          <el-col :xs="24" :sm="8" :md="8" :lg="8" :xl="8" style="display:flex;justify-content:center;">
            <div style="display:flex;flex-direction:column;align-items:center;width:100%;">
              <p class="p0"> Central Disturbance 0% </p>
              <video key='maze1' data-key='maze1' autoplay loop muted preload playsinline style="width:100%;max-width:550px;aspect-ratio:33/28;border-radius:0px;object-fit:cover;" controlslist="nodownload nofullscreen noremoteplayback noaudio noplaybackrate">
                <source src="/video/maze1.mp4" type="video/mp4">
              </video>
            </div>
          </el-col>
          <el-col :xs="24" :sm="8" :md="8" :lg="8" :xl="8" style="display:flex;justify-content:center;">
            <div style="display:flex;flex-direction:column;align-items:center;width:100%;">
              <p class="p0"> Central Disturbance 15% </p>
              <video key='maze2' data-key='maze2' autoplay loop muted preload playsinline style="width:100%;max-width:550px;aspect-ratio:33/28;border-radius:0px;object-fit:cover;" controlslist="nodownload nofullscreen noremoteplayback noaudio noplaybackrate">
                <source src="/video/maze2.mp4" type="video/mp4">
              </video>
            </div>
          </el-col>
          <el-col :xs="24" :sm="8" :md="8" :lg="8" :xl="8" style="display:flex;justify-content:center;">
            <div style="display:flex;flex-direction:column;align-items:center;width:100%;">
              <p class="p0"> Central Disturbance 30% </p>
              <video key='maze3' data-key='maze3' autoplay loop muted preload playsinline style="width:100%;max-width:550px;aspect-ratio:33/28;border-radius:0px;object-fit:cover;" controlslist="nodownload nofullscreen noremoteplayback noaudio noplaybackrate">
                <source src="/video/maze3.mp4" type="video/mp4">
              </video>
            </div>
          </el-col>
        </el-row>
        <div style="height: 6px;"></div>
        <el-row >
          <p class="p0">
          * The video is played at 1.5× playback speed. It shows a composite visualization including: (i) the BEV projection, static occupancy map, and dynamic obstacle motion predictions produced by the perception network (top-left); (ii) the globally fused static occupancy map (bottom-left); and (iii) the simulation environment, sparse skeleton graph, and planned trajectory (right).
          </p>
        </el-row>
        <el-row justify="center">
          <el-button type="primary" @click="restartMazeVideos" class="custom-button">Restart Videos</el-button>
        </el-row>
      </el-col>
    </el-row>
  </div>

  <div>
    <el-divider />

    <el-row justify="center">
      <h2 class="section-title" style="margin-bottom: 12px;">Real-World Experiments</h2>
    </el-row>

    <el-row justify="center" style="margin-bottom: 36px;">
      <el-col :xs="24" :sm="22" :md="20" :lg="18" :xl="16">
        <p style="margin-bottom: 16px;">
          Four representative real-world environments were constructed, featuring common static obstacles such as walls, tables, bushes, bicycles, and stone piers. A rectangular board pushed by a pedestrian was used as the dynamic obstacle. The unmanned vehicle operated at a maximum speed of 1 m/s.
        </p>

        <el-row justify="center" gutter="20" style="margin-bottom: 16px;">
          <el-col :xs="24" :sm="12" :md="12" :lg="12" :xl="12" style="display:flex;justify-content:center;">
            <div style="display:flex;flex-direction:column;align-items:center;width:100%;">
            <p class="p0"> BEV Scale 3.2 m × 3.2 m </p>
            <video key='real1' data-key='real1' autoplay loop muted preload playsinline style="width:100%;max-width:800px;aspect-ratio:47/18;border-radius:10px;object-fit:cover;" controlslist="nodownload nofullscreen noremoteplayback noaudio noplaybackrate">
              <source src="/video-real/room1.mp4" type="video/mp4">
            </video>
          </div>
          </el-col>
          <el-col :xs="24" :sm="12" :md="12" :lg="12" :xl="12" style="display:flex;justify-content:center;">
            <div style="display:flex;flex-direction:column;align-items:center;width:100%;">
              <p class="p0"> BEV Scale 3.2 m × 3.2 m </p>
            <video key='real2' data-key='real2' autoplay loop muted preload playsinline style="width:100%;max-width:800px;aspect-ratio:47/18;border-radius:10px;object-fit:cover;" controlslist="nodownload nofullscreen noremoteplayback noaudio noplaybackrate">
              <source src="/video-real/room2.mp4" type="video/mp4">
            </video>
          </div>
          </el-col>
        </el-row>
        <el-row justify="center" gutter="20" style="margin-bottom: 6px;">
          <el-col :xs="24" :sm="12" :md="12" :lg="12" :xl="12" style="display:flex;justify-content:center;">
            <div style="display:flex;flex-direction:column;align-items:center;width:100%;">
              <p class="p0"> BEV Scale 4.8 m × 4.8 m </p>
            <video key='real3' data-key='real3' autoplay loop muted preload playsinline style="width:100%;max-width:800px;aspect-ratio:47/18;border-radius:10px;object-fit:cover;" controlslist="nodownload nofullscreen noremoteplayback noaudio noplaybackrate">
              <source src="/video-real/outdoor1.mp4" type="video/mp4">
            </video>
          </div>
          </el-col>
          <el-col :xs="24" :sm="12" :md="12" :lg="12" :xl="12" style="display:flex;justify-content:center;">
            <div style="display:flex;flex-direction:column;align-items:center;width:100%;">
              <p class="p0"> BEV Scale 6.4 m × 6.4 m </p>
            <video key='real4' data-key='real4' autoplay loop muted preload playsinline style="width:100%;max-width:800px;aspect-ratio:47/18;border-radius:10px;object-fit:cover;" controlslist="nodownload nofullscreen noremoteplayback noaudio noplaybackrate">
              <source src="/video-real/outdoor2.mp4" type="video/mp4">
            </video>
          </div>
          </el-col>
        </el-row>
        <div style="height: 6px;"></div>
        <p class="p0">
          *  The video is played at 2.0× playback speed. It shows rear-view footage recorded by a handheld camera, constructed static occupancy maps, localization and mapping results generated by Fast-LIO2, as well as the overlaid skeleton graphs.
        </p>  
        <p class="p0">
          *  In the outdoor scenario, the maximum lateral exploration range is limited to 16 m. Nodes whose y-coordinates exceed ±16 m are not assigned frontier attributes. Consequently, in the final demonstration, the planner resorts to a backtracking strategy to search for a feasible path.
        </p>
        <el-row justify="center">
          <el-button type="primary" @click="restartRealVideos" class="custom-button">Restart Videos</el-button>
        </el-row>

      </el-col>
    </el-row>

  </div>

</template>