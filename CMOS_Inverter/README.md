# Incomplete Tutorial

# Advanced Design System (ADS) CMOS Inverter Tutorial
Building off from the previous tutorial showing how to create the [EKV MOSFET Model](https://github.com/J0NTrollston/ADS-EKV2.6-Model/tree/dd347d0c8e608031fab5bb2bc43bb72b4c067ee1/EKV_Models), we will go over how to create the CMOS Inverter and simulate it within You can also follow the steps through the tutorial on [YouTube](https://youtu.be/B8LCLi1V34s).

# Creating a simple Inverter
By using the previous NMOS and PMOS Models created using the Verilog-A code, we will create the CMOS Inverter in the ADS Schematic. 

## Create Inverter Schematic
1. In the same Workspace that you created the EKV Models, you will want to create a new Schematic. You can do this by Clicking *File* and navigating to *Schematic*

![New schematic](Images/New_Schematic.png)

2. Pull the NMOS and PMOS Models and place them into the Schematic
> 1. Click on the Display Component Library List on the top ribbon to grab the Models.
> 
>    ![Component Library](Images/Display_Component_Library_List.png)
>
> 2. This will open a Component Library Window which will have all of your libraries available in your Workspace. On the left, you will see a dropdown menu called All Libraries. If not already expanded, open this dropdown menu and Click on Workspace Libraries. To the right you will see the models. Double Click on the Component called nmos_ekv_va and place it down within the Schematic, then do the same for the pmos_ekv_va Component.

3. Now that we have our EKV Models in the Schematic, we will need to add the other components to test the Inverter.
> 1. Within the Schematic you will have the Palette to the left, use the dropdown to find the *Sources-Freq Domain* Palette. Once you have opened this menu, grab the 2 V_DC Components.
>
>    ![DC Volt Component](Images/Sources_Freq_Domain.png)
>
> 2. Go to the *Simulation-DC* Palette and grab the *D C* Components.
>
>    ![DC Component](Images/Simulation_DC.png)
>
>    After you placed the component, Double Click the Component and Open the Display Tab. Here is where you can choose what parameters are displayed on the Schematic. Choose SweepVar, Start, Stop and Step.
>
>    ![DC Display](Images/DC_Display.png)
>
> 3. There are some other items that we will need such as the *Ground* and *VAR* Components.
>    Grab one *Ground*
>
>    ![Ground Component](Images/Ground_Component.png)
>
>    And you will need one *VAR* Component
>
>    ![VAR Component](Images/VAR_Component.png)

4. Now that we have the components requred, we will need to put them together.
> 1. 
![p9](Images/CMOS_Inverter_Schematic.png)

## Simulate Inverter section
Later, I will add this section for the CMOS inverter using both models that we created. 



![p9](Images/CMOS_Inverter_VoutVsVin.png)



[^1]: [EFPL CMOS 0.5um Parameter Set](https://www.epfl.ch/labs/iclab/ekv/verilog-a/0_5um_cmos_par/)
[^2]: [GitHub FOSS EKVv2.6](https://github.com/ekv26/model)
[^3]: [EFPL EKV Examples](https://www.epfl.ch/labs/iclab/ekv/verilog-a/)
[^4]: [Altium Parameter Reference](https://techdocs.altium.com/display/AMSE/Metal+Oxide+Semiconductor+Field-Effect+Transistor+(MOSFET)+Model)
[^5]: [GMIN parameter](https://web.eece.maine.edu/~hummels/classes/ece342/docs/simetrix_simulatorreference.pdf)
