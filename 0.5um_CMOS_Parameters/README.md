Using the 0.5um EKV Model in ADS

As we will be using both nmos and pmos, we need to create 2 models. Let's first focus on the NMOS Model as the steps will essentially be the same.

NMOS Model:
In your workspace within ADS, navigate to File -> New -> VerilogA New
Create a new cell named "nmos_ekv_va" and paste the code located %%insert link to nmos_ekv_va.va code%%

Next, we will create a new schematic under the cell we created. Go ahead and add 4 pins and place them on the schematic view. These pin names will need to match what are used in the nmos_ekv_va.va file (d,g,s,b).
Below is a screenshot of what yours should look like. When this is complete, save and close the schematic.

%% schematic layout image %%
![alt text]([http://url/to/img.png](https://github.com/J0NTrollston/ADS-EKV2.6-Model/blob/main/0.5um_CMOS_Parameters/Images/SchematicLayout.png))

Under the same cell, create a new symbol. A Symbol Generator box will pop up, click okay and modify the symbol to look like an N-Type MOSFET.
Below is an example of what yours should look like. Save and close the symbol view once this is complete.

%% show example of nmos symbol %%

Now that we have all 3 files created, right click on the veriloga file we created initially and click Compile Verilog.
You should get a message stating that the code was compiled without errors. To confirm this, open the symbol view we created and navigate to File -> Design Parameters

The image below is what your Definition window should look like. Using the VerilogA file, ADS will pull the parameters used and save them for you.
Click OK on the Definition window to close.
%% nmos parameter view %%



PMOS Model:
I will quickly go over the PMOS Model as most of the steps are the same

Create a new cell named pmos_ekv_va and paste the code %% code link for pmos va file%% in a new veriloga file.
Save and then create the schematic and symbol views. The symbol for your pmos model should look the same as below.

%% pmos symbol %%

Once the pmos cell contains the 3 files as well, go ahead and compile the veriloga code and check the design parameters. Below is what the Definition window should look like.
Click OK and now you have your CMOS models created. Next let's test them out.
%% pmos Definition window of parameters %%

Simulating your models:

In order to simulate our models, we will need to create a new cell. Create a new schematic and in the cell box, rename your cell to "nmos_ekv_va_SIM"
In the schematic view, navigate to the Component Library Icon and under Workspace Libraries you will need to choose "nmos_ekv_va". Place the model in the schematic.

Next you will need to add the following components shown in the figure below. All required variables are displayed.

%% show sim layout of nmos %%

Once your simulation schematic looks like the one shown, you will need to complete one more step. Currently, the nmos schematic you placed down is an instance. This means you will need to reference the model before simulation.
Select the nmos instance on the schematic and Choose View for Simulation from the top ribbon. You will need to choose the veriloga file to use for simulation.

Your schematic should now have the text "veriloga" above the nmos if done correctly as shown below.

%% nmos simulation veriloga %%


Save and click simulate. You will want to plot the Drain Current vs the Voltage from Drain to Source (i.e. I_D vs V_DS)

%% show curve for nmos %%

We will do the same for the pmos simulation, rename your cell accordingly and replicate the schematic simulation below.

%% schematic for pmos simulaiton %%




Later, I will add this section for the CMOS inverter using both models that we created. 
