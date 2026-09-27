# EDGE AI — Federated Learning

This repository contains a hands-on lab introducing the basic concepts of **Federated Learning (FL)** using the **MNIST handwritten digit dataset**.

The goal of the lab is to first understand the limitations of training models independently on distributed and **Non-IID data**, and then demonstrate how Federated Learning can improve learning by allowing multiple clients to collaboratively train a shared model without directly sharing their local data.

## Lab Overview

The lab is divided into two main parts:

### 1. Independent Local Training on Non-IID Data

We first simulate multiple clients, where each client owns only a portion of the MNIST dataset.

The data is intentionally distributed in a **Non-IID (Non-Independent and Identically Distributed)** way, meaning that different clients may contain different digit classes or data distributions.

Each client trains its own local neural network independently.

This experiment demonstrates an important limitation of isolated local training:

> A model trained only on limited local data may perform well on its own distribution but generalize poorly to the complete global dataset.

### 2. Federated Learning

Next, we introduce a simple Federated Learning system.

Instead of keeping completely independent models, clients:

1. Receive a shared global model.
2. Train the model using their own local MNIST data.
3. Send their updated model parameters to the server.
4. The server aggregates the client models.
5. The updated global model is distributed back to the clients.

This process is repeated for multiple communication rounds.

The experiment demonstrates how Federated Learning allows distributed clients to collaboratively improve a shared model while keeping their original training data local.

## Dataset

We use the **MNIST** dataset, which contains grayscale images of handwritten digits from **0 to 9**.

The repository includes the MNIST data required for the lab.

## Learning Objectives

After completing this lab, participants should understand:

- The difference between local and collaborative model training
- What **Non-IID data** means in distributed machine learning
- Why independently trained local models can have poor global generalization
- The basic architecture of a Federated Learning system
- The roles of **clients** and the **central server**
- How model parameters can be aggregated across clients
- How Federated Learning can improve a global model without collecting all client data in one place

## Repository Contents

- `FL HelloWorld Program1 - Independent Local Training on Non-IID Data.ipynb`  
  Demonstrates independent local training and its limitations under Non-IID data.

- `FL HelloWorld Program2 - FL system.ipynb`  
  Implements a simple Federated Learning system and demonstrates collaborative model training.

- `FL Lab- Environment Setup.pdf` / `.docx`  
  Instructions for preparing the environment required for the lab.

- `MNIST_data/`  
  MNIST dataset files used in the experiments.

## Main Idea

The lab follows a simple progression:

**Distributed Data → Independent Local Training → Observe the Problem → Federated Learning → Shared Global Model**

This provides a practical introduction to why Federated Learning is useful when data is distributed across multiple devices, users, or organizations.
