---
layout: project
title: MAE 4272 Wind Turbine Design
description: Design of small scale wind turbine blades
technologies: [Inventor, 3D Printing, Wind Tunnel Testing, Python Data Analysis]
image: /assets/images/turbine_blade.jpg
---
**Blade Design Project Overview**

Our four-person team was tasked with designing and testing a small scale wind turbine blade to maximize the power generation under a given wind speed distribution while meeting safety constraints. We selected the SD7037 airfoil, designed the blade’s chord and pitch distribution, performed a structural analysis, and conducted tests in a wind tunnel to evaluate performance. Despite challenges in the testing phase, we gained valuable insights into the impact of modeling assumptions on model correlation with reality.

**My Contribution**
Over the course of this project, I was responsible for conducting structural analysis of the blade and designing the testing program. My analaysis ensured that the blade design adhered to the structural constraints using airfoil theory and a cantilever beam in bending model of the blade. I worked on identifying potential failure points and ensuring the blade’s structural integrity through a Python. Although we didn’t run full ANSYS simulations during this project, I believe that such simulations would be a crucial next step for validating the design more thoroughly and understanding resonant modes.

My other main contributions were focused on test plan development, data analysis, and structural analysis of the wind turbine blade. I wrote the test plan for our blade design based on information provided about the wind tunnel capabilities and our group testing goals. Once we collected the data, I also took charge of data analysis, focusing on post-processing the power and RPM curves. I compared experimental results with our initial model to evaluate the accuracy of our assumptions and identify any discrepancies between the predicted and actual performance of the blade.

**Design Process**

The primary challenge in our blade design was choosing the optimal airfoil and how to adjust its pitch and chord along the length of the blade. We first determined the value of three key parameters: effective wind speed, blade rotation rate, and Reynolds number. To determine the effective wind velocity, we integrated under the wind speed distribution to find the mean value and added a tolerance window to account for real-world variations. Next, we chose our the Tip Speed Ratio (TSR) and our operational blade rotation rate of 1400 RPM (well below the 3000 RPM safety limit).
We then calculated the global effective Reynolds number (Re=17000) by weighting the local Re values along the length of the blade. With this data, we scaled airfoil performance charts for several different airfoils (CL and CD) and chose the airfoil which had the highest average CL/CD ratio over a range of AoAs. This led us to choose the SD7037 airfoil for its robust performance under variable operating conditions. We then used equations taught in the Cornell wind power course to calculate the blade pitch and chord for the expected wind conditions. Finally, we performed a cantilever beam analysis on the blade under the expected lift forces to ensure it wouldn't break at the expected wind speeds and rotation rates.

**Testing Summary**

The blade was tested in the Big Blue wind tunnel to assess its performance across a range of wind speeds. These speeds were chosen to be near the mean of the wind speed distribution since these conditions are more likely to occur. Testing was complicated by friction issues and high free-spin RPMs, which led to challenges in starting the blade and managing resonance. At certain wind speeds, we observed unusual vibrations that affected power output. Despite these issues, we successfully measured power curves at wind speeds up to 4.5 m/s. The data we recorded is included in the plot below.
<img src="{{ site.baseurl }}/assets/images/blade-power-curve.jpg" alt="Blade Experimental Power Curve" width=400 style="display: block; margin: 0 auto; max-width: 80%; height: auto;">

**Results**

After processing the power curve data, several discrepancies between our model and experimental results became apparent. While the general shape of the power curves followed expectations, we observed a significant dip in power between 2200-2500 RPM, which correlated with the blade's resonant frequency. This indicated that vibration losses were impacting efficiency, something we hadn't accounted for in the design. 

<img src="{{ site.baseurl }}/assets/images/power-curve-vs-model.jpg" alt="Experiment and Model Comparison" width=400 style="display: block; margin: 0 auto; max-width: 80%; height: auto;">

Additionally, our experimental data showed lower power output than predicted, likely due to a combination of factors including friction issues during testing, a mirroring error in the blade's CAD design, and inaccurate assumptions in our model. We assumed a fixed Reynolds number, rotation rate, and no losses associated with constricted flow, tip effects, or blade wake; these do not hold true for our wind tunnel testing. When comparing cumulative power predictions, the model significantly overestimated the expected output, predicting 3.67 W compared to the experimental value of 0.213 W. This gap highlights the importance of refining our modeling assumptions, running structural simulations to avoid resonance issues, and improving the blade’s aerodynamic efficiency in future iterations.

**Conclusion & Reflection**

In terms of group dynamics, we worked well together as a team, with each member taking ownership of specific parts of the design and testing process and getting their work done in a timely manner. Despite some setbacks during the testing phase, we learned valuable lessons about blade design and performance. One major takeaway is that small discrepancies in modeling assumptions can have significant real-world effects. A CAD error in our blade, where the profile was mirrored, had a substantial impact on aerodynamic efficiency. We also noticed that our assumptions about wake, tip, and viscous effects led to our model over-predicting reality. Moving forward, we would correct these modeling errors by developing a more comprehensive model and make use of more advanced simulation tools (e.g., ANSYS) to ensure better predictions of blade performance and strength.