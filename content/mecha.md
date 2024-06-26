---
title: "MECHA"
date: 2023-07-28
draft: false
sections:
  - name: "MECHA Overview"
    text: "MECHA is a mathematical model designed to compute the flow of water through various parts of individual cells in a complete root cross-section. MECHA calculates the root reflection coefficient (sr) and root radial hydraulic conductivity (kr) by combining root anatomical data with cell hydraulic properties. It simulates water flow at the cellular level, resulting in kr predictions that align with experimental findings. MECHA seamlessly transitions from cell-level hydraulics to the broader root cross-section, offering an in-depth view of water transport in roots. Here's a breakdown of how kr of roots are computed in MECHA:"
    list:
      - "**Cell-Level Hydraulic Network**: MECHA computes the flow of water through the walls, membranes, and plasmodesmata of each individual cell throughout a complete root cross-section. This detailed hydraulic network at the cell level provides the foundation for upscaling."
      - "**Parameterization with Experimental Data**: The model is parameterized using experimental cell-scale hydraulic properties. These properties include:Conductivity of plasma membranes (Lp), Conductivity of cell walls (kw), and Conductance of plasmodesmata (KPD)"
      - "**Predicting Root Hydraulic Properties**: From the detailed cell-level computations, MECHA predicts the root reflection coefficient (sr) and root radial hydraulic conductivity (kr) for the root cylinder approach used in plant-scale models. This prediction connects hydraulic theories across scales. "
      - "**Comparison with Experimental Data**: The simulated kr values from MECHA fall within the range of measured kr values for maize roots. The model's predictions are validated by comparing them with experimental data from literature."
      - "**Sensitivity Analyses**: MECHA conducts sensitivity analyses to quantify the impact of various cell hydraulic properties on kr. For instance, the model assesses the sensitivity of kr to the permeability of cortex cells (Lp) and other parameters."
      - "**Further Reference**: The image of root architecture level above as well as Mecha working details was taken from the following [publication.](https://doi.org/10.1002/pld3.334)"
    image: "images/mecha2.jpg"
    imageWidth: "700px"
    imageHeight: "350px"
    textPosition: "bottom"  
    
  - name: "MECHA File Structure"
    text: "To facilitate accurate simulations, MECHA employs a specific file structure. Familiarizing yourself with this structure can optimize your usage of the model."
    list:
      - "**INPUT FILES**: MECHA requires four parameter files stored in the /in folder:"
      - "General.xml: Covers general simulation parameters. [link to General.xml](https://github.com/MECHARoot/MECHA/blob/master/in/General.xml)"
      - "BC.xml: Sets boundary conditions for the simulation, determining if the soil is dry, wet, or partially in contact with the root. [Link to BC.xml](https://github.com/MECHARoot/MECHA/blob/master/in/BC.xml)"
      - "Geometry.xml: Defines the root section geometry parameters, allowing you to select the root section for the simulation.[Link to Geometry.xml](https://github.com/MECHARoot/MECHA/blob/master/in/Maize1_Geometry.xml)"
      - "Hydraulics.xml: Covers the hydraulic parameters of various simulation variables.[Link to Hydraulics.xml](https://github.com/MECHARoot/MECHA/blob/master/in/Hydraulics.xml)"
      - "**OUTPUT FILES**: MECHA saves output files in a folder specified in the General.xml input file, under the Output tag. These files include:"
      - "*.PVTK files: Geometry files compatible with Paraview."
      - "Macro_prop_i.txt files: These provide a summary of simulation results, incorporating the radial data (**root reflection coefficient and root radial hydraulic conductivity**)."
    textPosition: "right"

  - name: "Case Studies"
    text: "MECHA has been used in several studies to elucidate the complex dynamics of water movement in plants, ranging from root hydropatterning responses to the influence of specific proteins on water transport, and solving enigmas of water flow against potential gradients in plant roots:"
    list:
      - "[Emily C. Morris et al.](https://dial.uclouvain.be/pr/boreal/object/boreal%3A198453/datastream/PDF_01/view) utilized the MECHA model to simulate and analyze the asymmetric movement of water within plant roots. This enabled them to understand how variations in water availability on different sides of a root influence the development and positioning of lateral roots, a phenomenon known as hydropatterning."
      - "[L. Ding et al. (2020)](https://doi.org/10.1104/pp.19.01183) investigated how changes in a specific water channel protein in maize roots affect the plant's ability to absorb and transport water. They used the MECHA model to better understand these effects, revealing insights into how water moves through different parts of the root and how this movement influences the plant's overall water uptake and growth."
      - "[V. Couvreur et al. (2021)](https://doi.org/10.1101/2021.04.19.439789) resolved a longstanding enigma in plant physiology using the MECHA model. They demonstrated how water can move against expected water potential gradients in plant roots, a phenomenon previously unexplained. Their work revealed the crucial role of solute concentration gradients in facilitating this unexpected water movement, thereby reshaping our understanding of plant water uptake and transport mechanisms."

  - name: "Try MECHA Online with ShinyApps or Binder"
    text: "Interested in testing MECHA without any installations? Mecha [team](/Phenorob-DAA/members/) have the perfect solution for you – [ShinyApps](https://plantmodelling.shinyapps.io/mecha/) and [Binder](https://mybinder.org/v2/gh/HeymansAdrien/GranarMecha/main). In just one click, immerse yourself in an interactive environment, exploring the code and data of this model."
    image: "https://mybinder.org/static/logo.svg" # The official Binder logo
    imageWidth: "200px"
    imageHeight: "100px"
    textPosition: "left"   


  - name: "Limitations of MECHA"
    text: "Despite MECHA's prowess, it does have certain constraints:"
    list:
      - "**Dimension Limitation**: The current version of MECHA is suitable for addressing questions of water flow in root segments with little variation along the longitudinal axis in terms of hydraulic properties. This means it's primarily designed for root segments that don't have significant changes in hydraulic properties along their length, such as the distal differentiated 10 cm of maize roots grown in hydroponics, excluding the elongation zone."
      - "**Longitudinal Variations**: The model does not inherently account for longitudinal variations of hydraulic properties or root environment."
      - "**Focus on Hydraulics**: The model emphasizes the hydraulic properties of cells, potentially overlooking other environmental factors impacting plant water relations."
      - "**Data Dependency**: MECHA necessitates detailed and precise input data, incorporating assumptions that might not encompass the intricacies of real-world processes. The illustrations in the study focus on a limited number of default, high, and low parameter values from the literature. Although a wide range of cell hydraulic parameter values were tested, there might be limitations in capturing the full range of possible hydraulic behaviors in all root types."
---
