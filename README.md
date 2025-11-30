# 6-DOF Robotic Manipulator – MATLAB Simulation (FK, IK, Jacobian, Path Planning)

## 📝 Overview
This project implements a complete simulation environment for a 6-DOF industrial robotic arm using MATLAB.
It integrates Forward Kinematics, Inverse Kinematics, Jacobian computation, workspace analysis, CAD-based visualization, 
and 3D geometric path planning. The system can reconstruct or “draw” volumetric shapes such as spheres, cubes, cylinders,
tori, and pyramids by visiting thousands of points in space.

This project was built as part of the university curriculum to deeply understand robotics kinematics, computational geometry, 
and simulation engineering.

---

## 🔧 Features
- Full **Forward Kinematics (FK)** using Denavit–Hartenberg parameters  
- Complete **Inverse Kinematics (IK)** using hybrid analytical + geometric methods  
- **Jacobian Matrix** for velocity & singularity analysis  
- Realistic **3D visualization** using CAD-based STL models from SolidWorks  
- **Workspace feasibility checks** & joint limit validation  
- End-to-end **trajectory planning** for multiple 3D shapes  
- Modular folder architecture for easy debugging and expansion  
- Link-wise **linear & angular velocity** computation  
- High-speed simulation engine using MATLAB matrix operations

---

## 🛠 Tech Stack
- **MATLAB**
- **SolidWorks** (STL model generation)
- Linear Algebra & DH Modelling  
- Geometric IK  
- 3D Path Planning  
- MATLAB Visualization Toolbox

---

## 📂 Folder Structure
/1_Kinematics_Core
├── getTi_i_1.m # DH transformation matrix
├── anotherApproch.m # Forward Kinematics engine
├── inverseKinematics.m # Analytical + geometric IK solver
├── jacobianMatrix.m # 6x6 Jacobian computation

/2_Utility_Functions
├── max_and_min.m # Joint limits & workspace bounds
├── workspace.m # Workspace visualization
├── workspacefinal.m # Reachability sampling
├── wristPositionEquations.m# Wrist center computation

/3_Visualization
├── stlread.m # STL importer
├── Rendering scripts # patch(), lighting, transforms

/4_SolidWorks_Source
├── SLDASM & SLDPRT files # Robot CAD components

---

## 🤖 Kinematics Overview

### **1. Denavit–Hartenberg Modelling**
Each link uses standardized DH parameters.  
It ensures alignment between:
- Mathematical kinematics  
- CAD STL link geometry  

### **2. Forward Kinematics**
Computes joint transforms, end-effector pose, and updates the robot model.

### **3. Inverse Kinematics**
- Wrist center calculation  
- Geometric IK for joints 1–3  
- Orientation IK for joints 4–6  
- Real-value filtering & angle continuity  
- Stable solutions for thousands of trajectory points

### **4. Jacobian Matrix**
Used for:
- Linear & angular velocity computation  
- Singularity detection  
- Advanced control extensions  

---

## 🎨 Visualization
- CAD-accurate STL models  
- Smooth shading, lighting & camera control  
- Dynamic link movement based on transforms  

Creates an industrial-grade appearance.

---

## 🔷 3D Path Planning
Implemented planners:

### ✔ Sphere – spiral sweep  
### ✔ Cube – face-by-face grid sweep  
### ✔ Cylinder – spiral → helical → reverse spiral  
### ✔ Torus – major/minor angle sweep  
### ✔ Pyramid – concentric layers / face sweep  

Generates dense point clouds for volumetric rendering.

---

## ▶️ Simulation Pipeline
1. Fetch next target point  
2. Compute IK  
3. Check feasibility  
4. Apply FK  
5. Transform STL models  
6. Plot trajectory  
7. Loop  

---

## 📊 Results & Observations
- Stable IK with no crashes  
- Smooth continuous motion  
- Accurate CAD rendering  
- Dense, clean 3D shape reconstruction  
- Correct velocity plots via Jacobian  

---

## 📚 Learnings
- FK/IK implementation from scratch  
- Path planning for geometric shapes  
- MATLAB–CAD integration  
- Simulation architecture  
- Robotics math fundamentals  

---

## 🔮 Future Enhancements
- Collision detection  
- Physics-based dynamics  
- G-code export  
- Speed optimization using curvature  

---


## 🏁 Conclusion
This project demonstrates deep integration of classical robotic kinematics, CAD visualization, and algorithmic 3D path planning into a unified MATLAB platform. It serves as a foundation for research, education, and advanced robotic motion generation.
