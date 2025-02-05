# Relics of Reionization in Cosmic Dawn III: Physical Properties of the Remnants of Photo-Evaporated Filaments and Structures
Master's thesis of [Vishrut Bezbarua](https://vishrut-b.github.io).

#### Supervisors : [Dr. Pierre Ocvirk](https://astro.unistra.fr/fr/recherche/pierre-ocvirk/) and [Dr. Katarina Kraljic](https://astro.unistra.fr/fr/recherche/katarina-kraljic/)

_This description of the thesis is supposed to summarise the entire work, as a means to present it to potential collaborators._
- The thesis report is available 
  <a href="https://github.com/vishrut-b/Master-Thesis/raw/main/Relics_of_Reionisation_in_CoDa_III (1).pdf" download>
    here
  </a>.
- Programming/libraries : Python (numpy, scipy, matplotlib, pandas, scikit-learn)
- Data source : [Cosmic Dawn III (CoDaIII)](https://coda-simulation.github.io/) simulation.
- Additional tool : [DisPerSE](https://www2.iap.fr/users/sousbie/web/html/index3c4a.html?category/Overview)

## Introduction
<figure style="width: 50%; float: left; margin: 0 15px 15px 0;">
  <img src="assets/css/Cartoon1.png" alt="cartoon" style="width: 100%;">
  <figcaption style="text-align: justify; font-size: 0.8em; font-style: italic; font-weight: 300; color: #666; margin: 10px 0 0 0;">Figure 1: A cartoon to illustrate an evolving filamentary network</figcaption>
</figure>

Cosmic filaments are fundamental components of the [large-scale structure](https://science.nasa.gov/universe/galaxies/large-scale-structures/) of the Universe, forming the network known as the [cosmic web](https://science.nasa.gov/resource/cosmic-web/). These elongated structures, which stretch over vast distances, play a pivotal role in shaping galaxy formation and evolution, as gas flows primarily through these filaments to feed galactic haloes and accelerate star formation within. A lot of their properties also remain open to speculation, for example, why do they not collapse under their own gravity or fragment into smaller bits and pieces? 

This thesis therefore investigates the evolution of [cosmic filaments](https://en.wikipedia.org/wiki/Galaxy_filament) through the [Epoch of Reionization (EoR)](https://en.wikipedia.org/wiki/Reionization), a transformative period in the history of the Universe when the first stars and galaxies emerged, producing ionizing radiation that altered the state of the IGM from cold to hot and rom neutral to ionised. Using data from the [Cosmic Dawn III (CoDaIII)](https://coda-simulation.github.io/) simulation—a high-resolution, cosmological coupled radiation-hydrodynamics simulation—the study aims to understand how the inhomogeneous reionization process impacts the physical characteristics of cosmic filaments and haloes. By analyzing their evolution across multiple redshifts (z = 15, 9, 7, and 5), my thesis tries to address how their density, temperature, and ionization state evolve over time, and what these changes reveal about the dynamics of the cosmic web.

<!-- <img src="assets/css/Cartoon1.png" alt="Cartoon" style="width:50%; display:block; margin:auto;"> -->

The scope of this study includes a sub-region (spanning roughly 3 comoving Mpc across each axis) of the CoDaIII simulation box, chosen to balance computational constraints with the need for detailed analysis. Through this focused investigation, the research contributes to a broader understanding of the role of cosmic filaments in the hierarchical assembly of matter in the Universe, particularly during a period characterized by rapid and spatially variable reionization.

## Methodology

<!-- Floated container with two images side by side and a single caption -->
<figure style="
  float: left; 
  display: flex; 
  flex-direction: column; 
  justify-content: center; 
  align-items: center; 
  width: 45%;     /* Reduced width so text can wrap on the right side */
  margin: 0 20px 20px 0; 
">
  <div style="
    display: flex; 
    justify-content: center; 
    align-items: center; 
    gap: 2%;
  ">
    <img src="assets/css/before.png" 
         alt="Basic definition of a filament"
         style="height: 500px; width: auto; display: block;">
    <img src="assets/css/after.png" 
         alt="Differences in networks based on persistence thresholds"
         style="height: 500px; width: auto; display: block;">
  </div>
  <figcaption style="text-align: justify; font-size: 1em; font-style: italic; font-weight: 300; color: #666; margin: 10px 0 0 0;">
    Figure 2: Comparison of IGM before and after reionization along with the extracted filamentary structures (overplotted in black) extracted using DisPerSE.
  </figcaption>
</figure>


<!-- Text that appears before the floated images -->
With a resolution sufficient to resolve individual filamentary structures, CoDaIII employs the RAMSES-CUDATON code to couple radiation transport, hydrodynamics, and dark matter dynamics. This allows the simulation to account for the escape of ionizing radiation from thousands of galaxies and the subsequent impact on their surrounding environments.
  
- The first step in the analysis involved extracting the filamentary network 
using <a href="https://www2.iap.fr/users/sousbie/web/html/index3c4a.html?category/Overview">DisPerSE</a> 
(DIScrete PERsistent Structures Extractor), an open-source tool that identifies 
critical points and connects them to delineate filamentary structures. This 
approach relies on persistence analysis to distinguish meaningful features 
from noise within the simulation’s density field. By setting a uniform 
persistence threshold across all analyzed redshifts, my study ensured 
consistency in identifying filaments while enabling comparisons of their 
properties over time.

- An important step in this project was the categorisation of filaments based on their baryonic density. The entire network is composed of various prportions of low and high density regions. Lower density sections of the network cannot be expected to display the same changes as the higher density counterparts as time progesses through reionization. Hence, the networks in all of the four redshifts were segregated into five density bins, the ranges of which were selected taking into account the overall density distribution of the complete IGM, and density thresholds for star formation and galaxy formation.

<!-- <div style="display: flex; justify-content: center;">
  <figure style="text-align: center; width: 48%; margin: 0;">
    <img src="assets/css/Cartoon2.png" alt="Elbow Method Graph" style="width: 100%;">
    <figcaption>Figure 1: Basic definition of a filament</figcaption>
  </figure>
</div>
-->

<img src="assets/css/Cartoon2.png" alt="Elbow Method Graph" style="display: block; margin: auto; width: 30%;">

- Once the filaments were identified and well categorised, their spatial and thermodynamic properties were analyzed using radial profiling techniques. This involved characterizing the regions around each filament for parameters such as baryonic density, dark matter density, temperature, neutral fraction, and metallicity. Figure 3 shows the median radial profiles for the different asociated properties of the filaments in the four redshifts, showcasing how these profiles evolve with time. The darker profiles represent the denser filament parts, while the fainter profiles represent the rarer parts.


## Results

<figure style="width: 50%; float: left; margin: 0 15px 10px 0;">
  <img src="assets/css/profiles.png" alt="Elbow Method Graph" style="width: 100%;">
  <figcaption style="text-align: justify; font-size: 0.8em; font-style: italic; font-weight: 300; color: #666; margin: 10px 0 0 0;">
    Figure 3: Median radial profiles for Gas density (first row), Dark matter density (second row), neutral fraction (third row),
    ionisation fraction (fourth row), temperature (fifth row), a magnified version of the same temperature profiles
    (sixth row), and metallicity of filaments in the simulations at redshifts 15, 9, 7 and 5. The radius represents the
    cylindrical radius, perpendicular to the filament in comoving kiloparsecs. The multiple lines in each panel represent profiles from filaments with
    different densities, with lower density parts indicated by more transparent lines.
  </figcaption>
</figure>


The study revealed several important trends in the evolution of cosmic filaments. As the Universe transitioned from a neutral to an ionized state, the density distribution of the filamentary network changed significantly. Higher-density filaments became more prevalent over time, reflecting the effects of gravitational collapse and radiative feedback from ionizing sources. By contrast, lower-density regions of the network diminished, likely due to the combined effects of radiation pressure and the hierarchical growth of structure.

The most important results have been shown in Figure 3. Temperature profiles showed a clear increase as a function of decreasing redshift, highlighting the progressive heating of the IGM by ionizing sources. High-density filaments developed distinct thermal envelopes, with peak temperatures observed at increasing distances from their central axes over time. Interestingly, while lower-density filaments also experienced heating, they lacked the pronounced temperature peaks seen in their higher-density counterparts.

The analysis of neutral fraction profiles revealed a shift in the ionization pattern as reionization progressed. At z=9, neutrality decreases across all densities, yet the densest regions are the most ionized. This arises because the IGM is still transitioning from neutral to ionized, with ionizing fronts expanding out from dense, source-rich filament regions. As a result, ionization proceeds inside-out: underdense areas remain neutral longer, until the advancing fronts eventually reach them. By **z=7**, the intergalactic medium (IGM) reaches a nearly uniformly ionized state, with ionizing photons forming a pervasive background. At this stage, gas density becomes the dominant factor influencing the neutral fraction: $x_\mathrm{HI} \propto \frac{\rho_\mathrm{gas}}{\rho_\mathrm{radiation}}$. This results in an **outside-in reionization pattern**, where lower - density regions—less shielded and more exposed — are the most ionized. This reverses the earlier trend, making the least dense areas the least neutral. The decline in neutrality continues consistently through **z=5**. A persistent observation across **z=9**, **z=7**, and **z=5** is that **filament spines remain more neutral** than their surroundings, irrespective of density.


Metallicity profiles provided additional insights into the effects of stellar feedback on the filamentary network. Only the highest-density filaments exhibited significant levels of metallicity, reflecting their connection to regions of active star formation. The presence of metals in these regions likely contributed to the observed temperature peaks, although the exact role of supernova feedback remains uncertain.

## Conclusions

This thesis underscores the importance of cosmic filaments as dynamic and evolving structures within the cosmic web. By leveraging the capabilities of the Cosmic Dawn III simulation and advanced data analysis techniques, the study provides a detailed characterization of how filaments respond to the spatially and temporally variable reionization process. The findings highlight the dual influence of gravitational dynamics and radiative feedback in shaping the physical and thermodynamic properties of filaments, offering new insights into their role as conduits of matter and energy in the Universe. While the results are based on a limited sub-region of the CoDaIII simulation, they serve as a foundation for future studies aimed at generalizing these findings to larger volumes and exploring additional properties, such as gas velocity. Moreover, the methodologies developed in this research have broader applications in the study of large-scale structure, demonstrating the transferability of these data science techniques to other cosmological simulations and observational datasets. In summary, this research contributes to our understanding of the cosmic web during the EoR and provides a framework for further exploration of the complex interactions between radiation, matter, and gravity in shaping the Universe’s largest structures.

## Key References

1. [How to Quench a Dwarf Galaxy](https://academic.oup.com/mnras/article/494/2/2200/5780248) 
2. [Rivers of gas – I. Unveiling the properties of high redshift filaments](https://academic.oup.com/mnras/article/502/1/351/6074265)
3. [Cosmic Dawn (CoDa): the first radiation-hydrodynamics simulation of reionization and galaxy formation in the Local Universe](https://academic.oup.com/mnras/article/463/2/1462/2892403)
4. [Cosmic Dawn II (CoDa II): a new radiation-hydrodynamics simulation of the self-consistent coupling of galaxy formation and reionization](https://academic.oup.com/mnras/article/496/4/4087/5836727)

and many more. 

---
There are always things worthy of being added into this summary, and always better ways of condensing a complex situtation into a simple understandable sentence, which is why this webpage is always under constuction. If you have questions, please feel free to reach out.

Tel : +33783235990<br>
Email : vishrutbezbarua@gmail.com
