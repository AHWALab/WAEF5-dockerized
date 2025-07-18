# Iowa EF5 configuration model

This repository contains all materials needed for running the EF5 hydrological model for Iowa at a 90m resolution.

---

## Setup Instructions

### 1. Install Docker Desktop
1. Download Docker Desktop (~600MB) from the official website:  
   [Docker Desktop Download](https://www.docker.com/products/docker-desktop/)

2. Use the **Download Docker Desktop** button (no account is needed).

3. After installation, adjust Docker's resource settings to allocate at least 8 GB of RAM:
   - Open Docker Desktop.
   - Go to **Settings** > **Resources** > **Advanced**.
   - Adjust the **Memory** slider to **8 GB**.
   - Click **Apply & Restart**.

---

### 2. Download or Clone This Repository
You can either **download** or **clone** the repository to your machine.

#### **Option 1: Download**
1. Click the green **Code** button in this repository.
2. Select **Download ZIP** and extract the contents.
3. Ensure the extracted folder is in a location without spaces in its path (e.g., `model_repository`).

#### **Option 2: Clone**
1. Copy the repository URL under **Code > HTTPS**.
2. Run the following command in your terminal:
   ```bash
   git clone https://github.com/RobledoVD/WAEF5-dockerized.git
   ```
3. Place the cloned folder in a directory without spaces in its name.

**Important:** Avoid folder names with spaces, as this can cause errors when running the model.

---

### 3. Build the EF5 Docker Container

#### **macOS/Linux**
1. Open your terminal and navigate to the project's main folder.  
   Example for a folder on your Desktop:
   ```bash
   cd ~/Desktop/IowaEF5_dockerized/
   ```
2. Change into the `docker/` folder:
   ```bash
   cd docker
   ```
3. Execute the build script:
   ```bash
   bash build_ef5_container.sh
   ```
4. Follow the instructions on the terminal. Once the process completes, verify that the EF5 container image has been built by checking the **Images** pane in Docker Desktop.

#### **Windows**
1. Open File Explorer and navigate to the project's main folder.
2. Go into the `docker/` folder.
3. Double-click the `build_ef5_container.bat` file.
4. A command window will open to show the build process. After completion, check the **Images** pane in Docker Desktop to confirm the image has been built.

---

### Verifying the Build
After a successful build, you can verify the presence of the EF5 container in Docker Desktop:
1. Open Docker Desktop.
2. Navigate to the **Images** tab.
3. Look for an image named `ef5-container`.

---

The EF5 Docker image is now ready to be executed.

--- 
