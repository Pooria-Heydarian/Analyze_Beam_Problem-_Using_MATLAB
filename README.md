# Analyze_Beam_Problem_Using_MATLAB
This project aims to analyze beam problems in two-dimensional space. In this project, the user addresses the resolution of these problems by entering the problem's details.
The link below is a vidio toturial made by Mohammad_Younes_Heidari which shows how to use the app
<div align="center">
  <a href="https://www.youtube.com/watch?v=D04FDE091i0">
    <img src="https://github.com/Pooria-Heydarian_Mohammad_Younes_Heidari/Analyze_Beam_Problem_Using_MATLAB/assets/107268679/8d2c4dee-7053-418e-81a0-3c288867e5a4" alt="utube" width="60px">
  </a>
</div>

## Introduction
As part of the design of this program, approximately 150 hours have been invested by Mohammad_Younes_Heidari and me. The output of this project is an advanced program for analyzing various statically determined beam problems. This program has the capability to process various types of data, including:
- Beam length
- Support type and coordinates
- Applied force with angle, coordinates, magnitude, and user-defined unit
- Applied moment with type (clockwise, counterclockwise), magnitude, and user-defined unit
- Distributed load with type (upward or downward), start and end coordinates, load function, and user-defined unit
- User-specified section coordinates
  
It can provide the following outputs:

- Ability to access and edit data by the user
- Plotting the beam diagram and all input data after each retrieval
- Solving the beam problem and displaying the unknowns
- Plotting axial and shear force diagrams and bending moment diagram
- Displaying the maximum and minimum values of axial and shear forces and bending moments
- Displaying user-specified section data (axial force, shear force, and bending moment at arbitrary coordinates).

## Description of Actions and Events:
For the design and development of this program, MATLAB has been utilized. Initially, a simple framework was employed to gather user input for problem-solving. Subsequently, specific data for each section is collected, stored in designated tables, and displayed. The data is stored in Excel files and is then calculated in another program. The program proceeds to draw shear force, axial force, and bending moment diagrams. It displays the magnitude of moments, support forces, as well as maximum and minimum values of shear forces and bending moments in various tables.

This program is capable of handling accurate input for beam length in units of meters, feet, and inches. It also handles point force values, angles, and directions in Newtons and pounds, visualizing them accordingly. Moreover, it accommodates point moment values in Newton.meters, pound.inches, and pound.feet units. Additionally, the program supports distributed load values in Newtons per meter, Newtons per foot, and Newtons per inch. The data is obtained and transferred to the problem-solving program, where they are stored in Excel files.

One of the significant challenges in problem-solving was plotting diagrams for point moments and distributed loads. To plot point moment diagrams, one-third circle segments are drawn based on the moment direction, followed by the addition of a quiver at the end. For drawing distributed load diagrams, a base graph is plotted, and a specific quiver length is added according to the wire's length.

An important note regarding the depiction and presentation of the beam and forces is that the thickness and size of the plotted diagrams should vary based on the beam's length.

## Problem Solving Method:
After receiving user input, the data is stored in several property-type variables, allowing access throughout the code. These data are then displayed below the input section in a table. The saved data is stored in Excel files, generated by the software itself. The second software is executed by the first software. The second software reads the stored data, solves the problem, and displays the beam.

This software, similar to the first one, draws the beam after receiving the data and enters the solve function. The solve function is the most crucial function of the project. The unknowns used in this function are created using symbolic arrays, allowing for problem-solving without limitations. This eliminates the need to reconstruct and address unknowns every time.

For calculating the unknowns, the vertical and horizontal force components and the moment at the beam's zero point are set to zero. The unknowns are then obtained and stored in property variables. Continuing, considering the number of data points, sections are defined at various points along the beam. For each section, forces and moments before the section are summed based on the x-coordinates. These values are then negated and considered as axial forces, shear forces, and bending moments at each section, which are displayed in the mentioned diagrams.

Additionally, to display maximum and minimum values, the MATLAB functions "max" and "min" are used. It is important to note the consideration of the absolute values of the desired diagrams.

## User Interface:

The main project interface (Figure 1-1) consists of the following sections:

1. Main Tabs (Model and Loads)
2. Sub-Tabs
   1. Tabs for Beam, Supports, and Sections under the main Beam tab
   2. Tabs for Point Load, Moment, and Distributed Load
3. Primary figure for displaying force and main beam model
4. Relevant tables for data display
5. "Add Section" button for each section
6. "Solve" button for problem-solving
7. "Unit" section for selecting the desired unit
   
This user interface provides an organized layout to interact with various aspects of the project, including defining the model, applying loads, displaying visualizations, inputting data, adding sections, performing problem-solving, and selecting units
<div align="center">
    <img src="https://github.com/Pooria-Heydarian/Analyze_Beam_Problem-_Using_MATLAB/assets/107268679/615514e5-7545-46e4-a2f1-fb6a6c403a44" alt="Figure1_1" width="70%" >
</div>




To begin, you input the length of the beam and then select the desired unit. Afterward, press the "Add" button. The beam is displayed as shown in Figure 1-2.


<div align="center">
    <img src="https://github.com/Pooria-Heydarian/Analyze_Beam_Problem-_Using_MATLAB/assets/107268679/d242b75f-dcf0-4119-abf1-b601a85de2cb" alt="Figure 1_2" width="70%">
</div>

### Support
In the "Support" section, you select the type of support. Enter the position of the support and then select the appropriate unit for its location. Afterward, you add the support. By changing the "Counter" value, you can add multiple supports. The information for each support is displayed in the table below the tab.

To modify the data for any of the supports, place the counter number next to the desired support number, then make the necessary changes to the data and press the "Add" button.

It's worth noting that there is no limitation on the number of supports you can enter. However, keep in mind that this program can only solve problems that are statically determinate. Therefore, these supports can only exist in two combinations:

1. One welded support
2. One pinned support along with one roller support

<div align="center">
    <img src="https://github.com/Pooria-Heydarian/Analyze_Beam_Problem-_Using_MATLAB/assets/107268679/33481a84-2035-4b1d-ba1e-c88e9898c713" alt="Figure 1_3" width="70%">
</div>

### Section
In the "Section" section, you can specify the location of a cross-section. The location of the cross-section is indicated by a multiplication sign (×) on the beam.

<div align="center">
    <img src="https://github.com/Pooria-Heydarian/Analyze_Beam_Problem-_Using_MATLAB/assets/107268679/f2680805-c2a2-463c-894a-60ac1916111c" alt="Figure 1_4" width="70%">  
</div>

### Load
In the next main tab, which is the "Load" tab, within the "Point Load" sub-tab, you enter the angle of the force with respect to the positive X-axis in the "Angle" section. Then, you input the position of the force's application and its magnitude with the desired unit, and add it. Figure 1-5 illustrates an example of two forces with different magnitudes and units at different positions.

An important note is that the unit displayed in the table is always in SI units.

<div align="center">
<img src="https://github.com/Pooria-Heydarian/Analyze_Beam_Problem-_Using_MATLAB/assets/107268679/96a0a848-aeca-4f21-bd47-828317411be3" alt="figure 1-5" width="70%">
</div>

### Moment
In the "Moment" section, you receive information about moments. After receiving the direction of the moments and other necessary information, you add the moments.

<div align="center">
    <img src="https://github.com/Pooria-Heydarian/Analyze_Beam_Problem-_Using_MATLAB/assets/107268679/8a659a60-f9d3-4305-8efd-14e60620e6f8" alt="Figure 1_6" width="70%">
</div>

### Distributed Load
In the "Distributed Load" section, you input information about distributed loads. Initially, you choose the direction of the force, then input the starting and ending points of the force, and finally enter the force equation.

Note: When entering the equation, keep in mind that the variable of the equation is "x", and for entering powers of "x", you should use "(^.)". For multiplication, it's better to use ".*".
<div align="center">
    <img src="https://github.com/Pooria-Heydarian/Analyze_Beam_Problem-_Using_MATLAB/assets/107268679/35f4938e-c81d-4605-bfa8-f0b2a5e3d544" alt="Figure 1_7" width="70%">
</div>

### Solve
After entering all the data, you press the "Solve" button and wait for the program to solve the problem. Once the program solves the problem, a new page opens displaying an analysis report. In this report, the following data are presented:

1. An illustration showing the overall beam diagram.
2. Shear force diagram.
3. Bending moment diagram.
4. Table containing support reactions (including horizontal force, vertical force, and moment at each support).
5. Table displaying maximum and minimum shear forces, axial forces, and bending moments present in the beam.
6. Table showing shear forces, axial forces, and bending moments at the section locations.

This comprehensive report provides a detailed insight into the analysis of the solved problem, helping you understand the distribution of forces, reactions, and bending moments throughout the beam.

<div align="center">
    <img src="https://github.com/Pooria-Heydarian/Analyze_Beam_Problem-_Using_MATLAB/assets/107268679/8d3ed5cd-2bdf-4674-aba0-6a0b9bb57f5d" alt="Figure 1_8" width="70%">

</div>
