# Kubernetes Downward API Lab

## 📌 Task Description
This repository contains the practical implementation of a Kubernetes task involving the **Downward API** to expose Pod-specific information directly to the containers.

**Requirements:**
1. Create a downward pv that uses the podIP and podName.
2. Create a claim that uses this pv.
3. Create a deployment that mounts this PVclaim and make sure that the podIP and podName are displayed in the index.html file.

*Technical Note: While the requirements mention a "downward PV," the Downward API in Kubernetes is implemented natively within the Pod specification using Environment Variables or volume projections. This lab fulfills the core requirement by injecting the data dynamically into the container and writing it directly to `index.html`.*

---

## 🚀 Step-by-Step Execution

### 1. The Deployment Manifest (`downward.yaml`)
A Deployment manifest was created to inject the Pod Name and Pod IP as environment variables using the Downward API `fieldRef`. A startup command was added to dynamically write these variables into the Nginx `index.html` file before launching the web server.

<img width="766" height="609" alt="Screenshot 2026-04-02 220023" src="https://github.com/user-attachments/assets/4833efca-eee0-4948-aa45-9f7af92483b0" />


### 2. Applying and Verifying

**Deploying and Testing the Application:**
The manifest was applied to the Kubernetes cluster. After retrieving the dynamically assigned Pod IP, a `curl` request was executed to verify that the Downward API successfully populated the `index.html` file with the real-time Pod Name and Pod IP.

<img width="770" height="162" alt="Screenshot 2026-04-02 220809" src="https://github.com/user-attachments/assets/df8373ac-691c-467f-9b0b-931b8c4961e5" />

---

## 👨‍💻 Author

**Marwan Tarek**
* 📧 **Email:** [marwantarek75@gmail.com](mailto:marwantarek75@gmail.com)
* 🐙 **GitHub:** [@marwantarek-eng](https://github.com/marwantarek-eng)
