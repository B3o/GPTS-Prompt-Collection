### GPT名称：NeRF and Vision Expert
[访问链接](https://chat.openai.com/g/g-WrqA5FpKg)
## 简介：在NeRF、高斯分布和计算机视觉方面的扩展专业知识
![头像](../imgs/g-WrqA5FpKg.png)
```text

1. Gaussian splatting
   Gaussian splatting is a volume rendering technique that deals with the direct rendering of volume data without converting the data into surface or line primitives.[1] The technique was originally introduced as splatting by Lee Westover in the early 1990s.[2] With advancements in computer graphics newer methods such as 3D and 4D Gaussian splatting have been developed to offer real-time radiance field rendering and dynamic scene rendering respectively.[3][4]

2. Development
   Volume rendering focuses on the generation of images from discrete samples of volume data that are usually sampled in three dimensions. This data can originate from a variety of sources such as CT scans or ozone density readings. Traditional methods transformed this volumetric data into lines and surface primitives to be displayed on computer graphics displays. However this approach sometimes introduced artifacts and hampered interactive viewing.[1]

   To address these issues direct rendering techniques which operate on the original volume data were developed. These methods are classified into two primary categories: feed-backward methods and feed-forward methods. The splatting algorithm being a feed-forward method is directly concerned with the rendering of rectilinear volume meshes. Splatting can be customized to render volumes as either clouds or surfaces by altering the shading functions providing flexibility in the rendering process.[1]

   Since its inception splatting has undergone various improvements. Some significant developments include textured splats anti-aliasing image-aligned sheet-based splatting post-classified splatting and the introduction of a splat primitive known as FastSplats.[2]

3. 3D Splatting
   Recent advancements in novel-view synthesis have showcased the utility of Radiance Field methods. To enhance visual quality while ensuring real-time display rates a new method was introduced that uses 3D Gaussians. This method integrates sparse points produced during camera calibration representing scenes with 3D Gaussians which retain properties of continuous volumetric radiance fields. Additionally, an interleaved optimization/density control of the 3D Gaussians was introduced along with a rapid visibility-aware rendering algorithm supporting anisotropic splatting.[3] This technique has shown potential in synthesizing high-quality 3D scenes from 2D images in real-time.[5]

4. 4D Gaussian Splatting
   Extending the concept of 3D Gaussian Splatting, the 4D Gaussian Splatting incorporates a time component allowing for dynamic scene rendering. It represents and renders dynamic scenes with a focus on modeling complex motions while maintaining efficiency.[4] The method uses a HexPlane to connect different adjacent Gaussians providing an accurate representation of position and shape deformations. By utilizing only a single set of canonical 3D Gaussians and predictive analytics, the 4D Gaussian splatting method models how they move over different timestamps.[6]

   Achievements of this technique include real-time rendering on dynamic scenes with high resolutions while maintaining quality. It showcases potential applications for future developments in film and other media although there are current limitations regarding the length of motion captured.[6]

5. See also
   Neural radiance field
   Volume rendering
   Computer graphics

6. References
   1. Westover Lee Alan (July 1991). "SPLATTING: A Parallel Feed-Forward Volume Rendering Algorithm" (https://articles.tomasparks.name/publications/Westover1991.pdf) (PDF). Retrieved October 18 2023.
   2. Huang Jian (Spring 2002). "Splatting" (http://web.eecs.utk.edu/~huangj/CS594S02/splattin g.ppt) (PPT). Retrieved 5 August 2011.
   3. Bernhard Kerbl; Georgios Kopanas; Thomas Leimkühler; George Drettakis (8 Aug 2023). "3D Gaussian Splatting for Real-Time Radiance Field Rendering". arXiv:2308.04079 (http s://arxiv.org/abs/2308.04079) [cs.GR (https://arxiv.org/archive/cs.GR)].
   4. Guanjun Wu; Taoran Yi; Jiemin Fang; Lingxi Xie; Xiaopeng Zhang; Wei Wei; Wenyu Liu; Qi Tian; Xinggang Wang (12 Oct 2023). "4D Gaussian Splatting for Real-Time Dynamic Scene Rendering". arXiv:2310.08528 (https://arxiv.org/abs/2310.08528) [cs.CV (https://arxiv.org/arc hive/cs.CV)].
   5. Papp Donald. "HIGH QUALITY 3D SCENE GENERATION FROM 2D SOURCE IN REALTIME" (https://hackaday.com/2023/09/02/high-quality-3d-scene-generation-from-2d-so urce-in-realtime). hackaday.com. Hackaday. Retrieved October 18 2023.
   6. Franzen Carl. "Actors' worst fears come true? New 4D Gaussian splatting method captures human motion" (https://venturebeat.com/ai/actors-worst-fears-come-true-new-4d-gaussian-s platting-method-captures-human-motion). venturebeat.com. VentureBeat. Retrieved October 18 2023.

   Retrieved from "https://en.wikipedia.org/w/index.php?title=Gaussian_splatting&oldid=1180792208"
```