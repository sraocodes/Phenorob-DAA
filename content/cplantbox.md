---
title: "CPlantBox"
date: 2023-07-28
draft: false

sections:  
  - name: "What is CPlantBox?"
    text: "CPlantBox is a full plant modeling framework that focuses on the growth and development of plant architectures, including both the root and shoot systems. It represents the plant as a single topological network of organs. The simulated plant architecture is made up of nodes or coordinates, and these nodes' properties and interactions form the entire network. For the root part, CPlantBox inherits the flexibility of CRootBox, allowing it to generate any type of root architecture. For the shoot, it has implemented various branching and leaf arrangement patterns. By combining these patterns, CPlantBox can simulate many types of shoot architectures. Further, the latest CPlantBox implementation provides linkage with different modules (photosynthesis and carbon flow) within a single framework, enhancing its capabilities and making it a versatile tool for plant studies. Visit the official [CPlantBox repository](https://github.com/Plant-Root-Soil-Interactions-Modelling/CPlantBox) for more information."
    textPosition: "right"
    image: "images/cpb_logo.png"
    imageWidth: "500px"
    imageHeight: "400px"
    textPosition: "bottom"

  - name: "How does it work?"
    text: "The workflow to use CPlantBox starts with generating input files, then interpreting parameters based on the input file. Following this, the model creates the topological structure from the seed or root, and finally, the output can be written to be visualized.The C-PlantBox framework requires specific data structures for its input to ensure accurate modeling. These structures define the parameters and conditions for both root and shoot systems simulation."
    list:
      - "**Parameter Set**: Defines plant-specific characteristics, such as growth rate, branching frequency, etc."
      - "**Environmental Data**: Information on soil type, humidity, light conditions, and other external factors."
      - "**Initial Conditions**: Defines the starting state of the plant system for simulation. This might include initial root length, shoot height, etc."
      - "**Temporal Data**: Information on how certain parameters might change over time, such as light cycles or seasonal changes."
    image: "images/cplantbox2.gif"
    imageWidth: "588px"
    imageHeight: "582px"
    textPosition: "bottom"

  - name: "CPlantBox features"
    text: "CPlantBox incorporated several modules, including those related to the effects of atmospheric variables and plant water status on coupled stomatal opening and photosynthesis. The novel aspect of this latest CPlantBox implementation is the linkage of all these modules within one framework. It aims to test genotype-environment-management interactions and their emergent properties. Technically, it uses graph formalism for organism representation, combining **C++** speed with **Python's** clarity. For example, it has been coupled with the carbon and water flow model, PiafMunch. This coupling allows for fast simulations on complex plant structures, including the simulation of carbon and water flows within the plant. The highlights:"
    list:
      - "It is capable of simulating the growth and development of a variety of plant architectures (root and shoot)."
      - "It is flexible and can be coupled with external modelling tools."
      - "It is open source, highly accessible and source code available on [github](https://github.com/Plant-Root-Soil-Interactions-Modelling/CPlantBox)."
    table:
      headers: ["Model/Module", "Purpose"]
      rows:
        - ["PiafMunch", "Handles the carbon and water flow dynamics within the plant and the soil-plant-atmosphere continuum. [learn more](https://doi.org/10.1093/insilicoplants/diad009)"]
        - ["DuMux (Soil Water Flow)", "A model for phloem flows driven by hydrostatic pressure gradients was adapted for tight coupling to CPlantBox."]
        - ["Stomatal Opening Regulation", "Regulates transpiration (water sink) and photosynthesis (sucrose source) based on atmospheric and leaf conditions."]
        - ["Xylem Water Flow", "Simulates the flow of water in the plant, including lateral root and leaf fluxes and soil-root water exchanges."]
        - ["Mesophyll and Sieve Tube Sucrose Flow", "Simulates the flow of sucrose in the plant."]
        - ["Carbon Partitioning (from other FSPMs)", "Became an emerging property in CPlantBox, allowing for simulations of growth variations based on conditions."]
        - ["Photosynthesis and Stomatal Opening", "A coupled photosynthesis (FvCB) and stomatal opening model was added to the CPlantBox."]
    image: "images/cplantbox3.png"
    imageWidth: "352px"
    imageHeight: "500px"
    textPosition: "bottom"

  - name: "Tight Coupling with other models"
    text: "The main objective of coupling CPlantBox with PiafMunch and Dumux is to simulate the carbon and water flow within the plant-soil system. PiafMunch is responsible for handling the carbon flow module within the plant while DuMux is used to simulate soil water flow. When coupled with CPlantBox, it allows for the simulation of the soil–plant–atmosphere continuum, considering both water and carbon fluxes. Similarly the objective of integrating the FvCB-stomatal regulation module with CPlantBox is to simulate the processes of transpiration and photosynthesis, particularly in the leaf blades, and to provide a comprehensive understanding of the plant's response to environmental conditions. Similarly Dumux module which is a flow and transport in porous media simulator is now integrated into the CPlantBox framework via a Python binding in order to represent the soil in which the plant roots are growing. This integrations now known by Dumux-ROSI. ROSI stands for Root-Soil Interaction. This synergy coupling enables to accurately represent soil and rhizosphere processes and their interactions with a growing root architecture. This installation guide provides a general overview for setting up DuMux-ROSI on Linux systems. For detailed instructions, refer to the [DuMux-ROSI Manual](https://github.com/Plant-Root-Soil-Interactions-Modelling/dumux-rosi/blob/master/Manual.pdf)."
    table:
      headers: ["Model", "Parameters Exchanged"]
      rows:
        - ["From **CPlantBox** to **PiafMunch**", "Information related to plant growth, structure, and current state which can influence carbon flow."]
        - ["From **PiafMunch** to **CPlantBox**", "Data on carbon flow, sucrose source, and potential carbon limitations."]
        - ["From **CPlantBox** to **DuMux**", "Information about plant growth, root structure, and water requirements."]
        - ["From **DuMux** to **CPlantBox**", "Data on soil water flow, availability, and potential water uptake by the plant."]
        - ["From **CPlantBox** to **FvCB**-Stomatal Regulation", "Information related to plant growth, structure, current state, and environmental conditions that can influence transpiration and photosynthesis."]
        - ["From **FvCB**-Stomatal Regulation to **CPlantBox**", ["**Net Assimilation Rate**: Represents the rate of carbon assimilation in the plant.","**Leaf Outer-Xylem Water Potential**: Indicates the water potential in the outer xylem of the leaf, influencing water movement within the plant."]]
    image: "images/cplantbox4.jpg"
    imageWidth: "885px"
    imageHeight: "576px"
    textPosition: "bottom"

  - name: "Case Studies"
    text: "CPlantbox has been used to simulate and analyze various aspects of plant growth and soil interactions in numerous studies:"
    list:
      - "[Khare et al. (2022)](https://doi.org/10.3389/fpls.2022.798741) utilized CPlantbox to model root water uptake in drying soil conditions. Their study, focusing on soil hydraulic conductivity and its effect on root water uptake, demonstrates the importance of accurate modeling in predicting plant responses to dry soil conditions."
      - "[De Bauw et al. (2020)](https://doi.org/10.1093/aob/mcaa120) employed CPlantbox for constructing a functional–structural model of upland rice root systems. This study underscores the impact of lateral roots and growing root tips on phosphate uptake, and how CPlantbox can be used to simulate root growth and nutrient uptake under varying soil conditions."

  - name: "Try It Online with Binder!"
    text: "If you'd like to explore and run CPlantbox without any installations on your local machine, CPlantbox team have a convenient solution for you – [Binder](http://b.cplantbox.com/)! With just a click, you can have an interactive environment to play with the code and data in this notebook. What are you waiting for?"
    list:
      - "**Introduction**: Delving deep into the basics to ensure a good grasp of the core plant modeling concepts."
      - "**Interactive Examples**: Modify and execute code to see real-time plant root and shoot growths."
      - "**Visualizations**: Python codes and vtk format output enables easy visualization of created plant architectures."
      - "**Exercises**: Apply what you've learned through simple exercises and examples."
    note: "Click the button below to launch this notebook on Binder. Make sure you have a stable internet connection for the best experience."
    image: "https://mybinder.org/static/logo.svg" # The official Binder logo
    imageWidth: "200px"
    imageHeight: "100px"
    textPosition: "left"

  - name: "CPlantBox lectures"
    text: "Explore the world of plant shoot and root architecture with insightful talks on the C-PlantBox modeling tool. Dive into the intricate mathematics and operational intricacies that power CPlantBox tool for simulating and analyzing whole plant growth dynamics by [clicking here](/videos/)🌱" 


---
