---

# 9S LiPo Battery Management System (BMS) - Altium Project

## Project Overview
This BMS design is based on the Texas Instruments reference project [TIDA-00449](https://www.ti.com/tool/TIDA-00449). Modifications have been made to adapt the design to specific 9S LiPo battery requirements and higher current thresholds. This BMS should be capable of handling high-current applications, providing essential protections (UV, OV, SCD, OCD), enabling idle cell balancing, and displaying State of Charge via 4 LEDs. 

## Features
- **Battery Configuration**: 9S1P LiPo Battery 33.3V [3x Zeee 3S 5200mAh Lipo Battery 11.1V 80C](https://a.co/d/2pvP0it)
- **Continuous Discharge Current**: 80A
- **Maximum Discharge Current**: 120A
- **Balancing current**: 150mA at 4.2V
- **Protection Settings**:
  - **Undervoltage (UV)**: 2.75V
  - **Overvoltage (OV)**: 4.3V
  - **Overcurrent Discharge (OCD)**: 333A for 40ms (based on 80% of maximum current for a 5200mAh, 80C cell)
  - **Short-Circuit Discharge (SCD)**: 400A for 200µs
- **Components**:
  - **Analog-Front-End (AFE)**: [BQ76930](https://www.ti.com/product/BQ76930)
  - **Microcontroller (MCU)**: [MSP430G2553](https://www.ti.com/product/MSP430G2553)
  - **Balancing Circuit**: External balancing using N-channel MOSFETs
- **Communication**:
  - **AFE <--> MCU**: I2C
  - **MCU <--> External Host**: UART
  - **Programming MCU**: JTAG, Spy-Bi-Wire

## Getting Started

### Prerequisites
- Install [Git](https://git-scm.com/) on your computer.
- Set up an account on [GitHub](https://github.com/) if you haven’t already.
- Import [Celestial Altium Library](https://github.com/issus/altium-library) into Altium.

### 1. Clone the Repository
To get a copy of the project onto your local machine, open a terminal (or Git Bash if on Windows) and use the following command:

```bash
git clone <repository-url>
```

Replace `<repository-url>` with the link to this GitHub repository. This command will create a folder with all project files on your local machine.

### 2. Create a New Branch
Before making changes, it’s a good practice to create a separate branch for your work. This keeps the main codebase stable while you work on new features or fixes.

```bash
git checkout -b <branch-name>
```

Replace `<branch-name>` with a name that describes the changes you’re making (e.g., `feature-balance-circuit` or `fix-uv-protection`). 

### 3. Make Changes and Commit
After editing files, save your changes, and use the following commands to stage and commit them:

```bash
git add .
git commit -m "Brief description of your changes"
```

- `git add .` stages all modified files.
- `git commit -m` saves the changes with a message describing what you did.

You can combine the `git add` and `git commit` commands with the `-am` option, which stages and commits changes in a single command. Here’s how:

```bash
git commit -am "Brief description of your changes"
```

The `-a` option automatically stages all modified (but not new) files, and `-m` lets you add a commit message. 

#### Important Note:
This command only stages files that have already been tracked by Git (i.e., files that were previously committed). If you add any new files, you’ll need to use `git add <filename>` first or just use `git add .` to stage everything before committing.

### 4. Push Changes to GitHub
When ready to share your work, push your branch to GitHub:

```bash
git push origin <branch-name>
```

This uploads your branch to the GitHub repository, where others can see your changes.

### 5. Create a Pull Request
On GitHub, go to your repository and you’ll see an option to create a "Pull Request" (PR) for your branch. This allows others to review your changes before they’re added to the main branch.

### 6. Merging Changes
If you’re ready to combine your changes with the main branch (often after a PR review), you can merge your branch:

- First, switch back to the main branch:

  ```bash
  git checkout main
  ```

- Then, merge your changes:

  ```bash
  git merge <branch-name>
  ```

Replace `<branch-name>` with the name of your branch.

### 7. Keeping Your Branch Updated
To pull in the latest changes from the main branch into your working branch:

```bash
git checkout <branch-name>
git pull origin main
```

This keeps your branch in sync with any updates made to the main branch by others.

## Libraries and Attributions
This project utilizes components from the [Celestial Altium Library](https://github.com/issus/altium-library). Special thanks to the contributors of this open-source library for providing high-quality and accessible resources for Altium designers.

## License
**[TBD]**

---
