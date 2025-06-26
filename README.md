# Smart Farming System with ML, IPFS, and Ethereum

A complete smart farming platform using Django (backend), React (frontend), Machine Learning models, IPFS (Pinata) for decentralized data storage, and Ethereum (Ganache/Web3.py) for blockchain integration.

## Features
- Crop prediction using ML
- Fertilizer recommendation
- Real-time sensor data from IPFS (Pinata)
- React-based interactive UI with wallet integration
- User-friendly dashboard (React)
- Time-restricted access control via smart contracts
- Blockchain-based data interaction

## Project Structure

The project is organized into the following main directories:

- `blockchain/`: Contains the Django backend application for handling business logic, interacting with the database, and serving the API.
- `contracts/`: Smart contracts written in Solidity for blockchain interaction.
- `dataset/`: Datasets used for training the machine learning models.
- `frontend/`: The React frontend application.
- `greenhash/`: The main Django project settings and configuration.
- `scripts/`: Scripts for deploying smart contracts.
- `shared_config/`: Configuration files, including deployed contract information.
- `templates/`: HTML templates (though the frontend is primarily React, this might be for basic Django views or testing).

## Technologies Used

### Development Environment
- **Project IDX:** A cloud-based development environment used for building and deploying the project.

### Backend
Our backend infrastructure relies on:
- **Python (>= 3.8):** The core programming language for server-side logic.
- **pip:** Python's package installer, used for managing project dependencies.
- **virtualenv (Recommended):** A best practice for creating isolated Python environments, ensuring project dependencies don't conflict.
- **Django (5.2):** A high-level Python web framework for rapid and robust development.
- **Django REST framework (3.16.0):** A powerful toolkit for building Web APIs.
- **django-cors-headers (4.7.0):** A Django app for handling Cross-Origin Resource Sharing (CORS) headers.
- **Gunicorn:** A Python WSGI HTTP server for deploying Django applications.

### Data Science & Machine Learning
For data processing and model building, we utilize:
- **NumPy (2.1.3):** A fundamental package for numerical computation in Python.
- **Pandas (2.2.3):** A library providing high-performance, easy-to-use data structures and data analysis tools.
- **Scikit-learn (1.6.1):** A comprehensive library for machine learning algorithms.
- **SciPy (1.14.1):** A library for scientific and technical computing.
- **Joblib (1.4.2):** A set of tools to provide lightweight pipelining of Python jobs.
- **threadpoolctl (3.6.0):** A library to limit the number of threads used by numerical libraries.

### Utilities & System
These libraries provide essential functionalities:
- **Requests (2.32.3):** A simple and elegant HTTP library for Python.
- **python-dateutil (2.9.0.post0):** An extension to the standard datetime module.
- **pytz (2025.2) & tzdata (2025.2):** Libraries for working with time zones.

### Blockchain Integration
To interact with the blockchain, we leverage:
- **Web3.py:** A Python library for interacting with Ethereum-like blockchains.
- **eth-account:** A library for managing Ethereum accounts and signing transactions.
- **IPFS HTTP Client:** A Python client for interacting with the InterPlanetary File System (IPFS).

### Frontend
Our user interface is built with:
- **Node.js (>= 18.x):** A JavaScript runtime environment.
- **npm:** The package manager for Node.js.
- **MetaMask Browser Extension:** A browser extension that acts as an Ethereum wallet, enabling interaction with decentralized applications.
- **Ganache ([https://trufflesuite.com/ganache/](https://trufflesuite.com/ganache/)):** A local blockchain emulator for development and testing.

### Version Control
- **Git:** A distributed version control system for tracking changes in code.

## Setup and Running Instructions

### Prerequisites
Log in to https://idx.google.com/, and select "`import repo`".

### 1. Clone the repository
```bash
git clone https://github.com/Mridul-IIT-DH/GreenHash.git
```

### 2. Run the commands
Execute the following commands in your terminal. After the docker system prune -a command shows some deleted images (typically within 10 seconds), press Ctrl + C to proceed with the next commands.
```bash
docker-compose down --volumes

docker system prune -a

docker-compose build --no-cache

docker-compose up
```

### 3. Configure IDX Public Ports (Only a one time process)

Once the `docker-compose up` command finishes execution:

1.  Click on the **Firebase studio** option in the left vertical bar (at the bottom).
2.  Expand the "**Backend ports**" option (also at the bottom).
3.  You'll see three ports: **3000**, **8000**, and **8545**. Click the **lock icon** next to each port to change its status from private to public.
4.  Click the "**open in new tab**" option (with an arrow) next to port **8000** and **copy** the URL.
5.  Open the file `/home/user/GreenHash/frontend/src/components/CropPredictor.jsx`.
6.  Locate the `fetch` function:
    ```jsx
    const response = await fetch("https://8000-firebase-greenhash-1748714759926.cluster-fdkw7vjj7bgguspe3fbbc25tra.cloudworkstations.dev/predict_crop/",
    ```
7.  Replace the URL part: `https://8000-firebase-greenhash-1748714759926.cluster-fdkw7vjj7bgguspe3fbbc25tra.cloudworkstations.dev/` with the URL you copied from port **8000**. **Ensure `predict_crop/` remains at the end of the URL.**

**Please follow the setup video to run the project.**

### 4. Setup video
YouTube link: https://youtu.be/wFDlBA4dgsQ

## MetaMask (Important)
It's crucial to understand that each time you restart your server, MetaMask needs a clean slate. Currently, neither MetaMask nor Chrome offers a direct way to clear its cache. Therefore, you'll need to remove the MetaMask extension and then reinstall it. Afterward, you'll need to set it up again, following the same initial instructions.

This step is necessary because IDX allocates a fresh network for Ganache every time the server starts. Consequently, the blockchain initializes on this new network. However, your MetaMask extension remains connected to the previous blockchain network. Reinstalling ensures MetaMask connects to the newly created network, allowing you to interact with the updated blockchain.

## 📞 Contact
For issues or contributions, feel free to open an issue or pull request.

👨‍💻 Team Members 
K. S. Pavithran   
📧 cs24mt006@iitdh.ac.in   
🔗 github.com/pavi-ks   

Mridul Chandrawanshi   
📧 cs24mt002@iitdh.ac.in   
🔗 github.com/Mridul-IIT-DH   


Kritika Mahajan   
📧 cs24mt023@iitdh.ac.in   
🔗 github.com/kritikacs24m023   

---

Happy Farming! 🌱🚜