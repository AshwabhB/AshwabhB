# Projects Overview

A summary of all my projects, including key descriptions and technologies used.

---

## 1. NeuraType — Speech-to-Text Desktop App

Feature-rich Windows desktop application for real-time speech-to-text transcription. Includes a PyQt6 GUI, support for 6 OpenAI Whisper models with CUDA GPU acceleration, a 7-stage NLP post-processing pipeline, dual LLM integration (GPT-4.1-mini cloud + local GGUF models via llama-cpp-python), global hotkeys, multi-threaded audio processing, and a packaged installer built with Inno Setup.

**Tech:** Python, PyQt6, OpenAI Whisper, PyTorch, CUDA, OpenAI API, llama-cpp-python, FFmpeg, multi-threading, Windows packaging

---

## 2. VoiceGeneration — GAN Voice Conversion Pipeline

A 5-module voice conversion pipeline covering the full audio-to-audio flow: Whisper ASR for transcription, GPT-2 Large for text generation, gTTS for synthesis, a speaker classification MLP using 46-dimensional audio features with ResidualBlocks, and a custom GAN voice converter built with a U-Net generator and spectrally-normalized discriminator. Trained on VoxCeleb1.

**Tech:** Python, PyTorch, GANs, OpenAI Whisper, GPT-2, gTTS, librosa, mel spectrograms, U-Net, spectral normalization, CUDA

---

## 3. YOLO Traffic Sign Detection

Custom YOLO11 object detection model (~5.4M parameters) built from scratch for traffic sign recognition. Introduces a novel C2DSA attention block and SAAL size-adaptive anchor assignment. Includes TTA inference and a two-stage out-of-distribution detection system (Cosine KNN achieving AUROC=0.9972 + Contrastive Projection Head). Developed over 15 documented iterations as a CS-297 research project.

**Tech:** Python, PyTorch, OpenCV, YOLO, attention mechanisms, contrastive learning, OOD detection, CUDA

---

## 4. FacePoison — Adversarial ML on Face Recognition

Implements the Poison Frog adversarial data poisoning attack against face recognition systems. Architecture uses ResNet101 with Channel/Spatial Attention and a Feature Pyramid Network. Perturbations are L-inf constrained and designed to align features in latent space. Training incorporates FocalLoss, Label Smoothing, and Mixup augmentation.

**Tech:** Python, PyTorch, ResNet101, adversarial ML, FPN, attention mechanisms, transfer learning

---

## 5. Cloud-Native Order Management API — AWS ECS Fargate

A production-grade cloud-native REST API for order management, developed across multiple iterations. Built with FastAPI and PostgreSQL, featuring idempotent order processing via SHA-256 fingerprinting, multi-table ACID transactions, and a two-tier caching strategy (in-memory TTLCache + CloudFront CDN). Deployed on AWS ECS Fargate with RDS PostgreSQL, an Application Load Balancer, CloudWatch logging, SSM parameter secrets, multi-stage Docker builds, and Alembic database migrations.

**Tech:** Python, FastAPI, PostgreSQL, AWS (ECS Fargate, RDS, ALB, CloudFront, CloudWatch, SSM), Docker, SQLAlchemy, Pydantic, Alembic, REST API

---

## 6. ParkSmart — SJSU Parking Prediction System

End-to-end serverless parking occupancy prediction system for SJSU campus garages. A CloudWatch-triggered AWS Lambda function scrapes real-time occupancy data from 4 garages every 15 minutes and stores it in S3. Four MLPRegressor models (one per garage) predict future occupancy from temporal features. A Streamlit dashboard surfaces historical trends and live ML predictions.

**Tech:** Python, AWS Lambda, S3, CloudWatch, Boto3, BeautifulSoup4, scikit-learn, MLPRegressor, joblib, Streamlit, Matplotlib, serverless, ETL

---

## 7. BookSurgeon — .NET Web Application

Full-stack web application built with ASP.NET Core MVC following a 4-layer N-tier architecture (Web, Services, Data, Common layers). Uses Entity Framework Core with the repository pattern and dependency injection throughout. Undergraduate capstone project.

**Tech:** C#, ASP.NET Core MVC, Entity Framework Core, SQL, HTML/CSS/JavaScript, N-tier architecture, dependency injection

---

## 8. WellsBot — Discord Bot Suite

A suite of 3 Python Discord bots demonstrating different architectural patterns: a polling-based AFK channel mover, an event-driven AFK mover using WebSocket, and an interactive soundboard with button UI and FFmpeg-powered audio streaming. Highlights the contrast between polling vs. event-driven designs in async Python.

**Tech:** Python, discord.py, asyncio, WebSocket, FFmpeg, audio streaming, event-driven architecture

---

## 9. Wine Quality Classification — Deep Learning

Neural network classifier that categorizes wine samples into 5 quality tiers. Uses a 64→32→5 architecture with Batch Normalization, Dropout (0.6), L2 regularization, early stopping, and ReduceLROnPlateau scheduling for stable training.

**Tech:** Python, TensorFlow, Keras, scikit-learn, Pandas, neural networks, regularization, multi-class classification

---

## 10. Perceptrons — From-Scratch Neural Networks

Implements single-layer and multi-layer perceptrons using only NumPy. Covers manual forward pass, sigmoid activation, MSE loss, and full backpropagation with the chain rule. A foundational educational project demonstrating core neural network mechanics without any ML frameworks.

**Tech:** Python, NumPy, backpropagation, gradient descent, neural networks from scratch

---

## 11. User Classification Model — MLP with Adversarial Augmentation

A from-scratch MLP (NumPy) that explores adversarial synthetic data augmentation using inverted labels to expand the training set. Presents a comparative pipeline between models trained on real data alone vs. synthetically augmented data.

**Tech:** Python, NumPy, MLP from scratch, synthetic data generation, adversarial augmentation, experimental design

---

## 12. Outlier Detection — Statistical Methods

Implements two outlier detection approaches from scratch: a parametric Z-score confidence interval method and a non-parametric DB(r,β) distance-based method. Applied to frequency distribution datasets for data quality analysis.

**Tech:** Python, Pandas, NumPy, SciPy, statistics, anomaly detection, outlier detection

---

## 13. Search Algorithms — BFS, DFS, A\*

Implementations of BFS, DFS, and A* graph search algorithms with pytest test suites. Covers priority queues, heuristic functions (Manhattan and Euclidean distance), and path reconstruction.

**Tech:** Python, algorithms, graph search, BFS, DFS, A*, data structures, pytest

---

## 14. Optimization Search Algorithms — Hill Climbing & Simulated Annealing

Three local search algorithms applied to a discrete optimization landscape: basic Hill Climbing, Hill Climbing with sideways moves, and Simulated Annealing with Boltzmann acceptance criterion. Includes real-time matplotlib animation to visualize the search process.

**Tech:** Python, optimization, hill climbing, simulated annealing, Boltzmann acceptance, matplotlib visualization

---

## 15. Stable Matching — Gale-Shapley Algorithm

Implementation of the Gale-Shapley stable matching algorithm extended to support multi-slot quotas (modeled after the NRMP residency match). Includes 10 test scenarios with unittest validation covering quota ranges from 0 to 4. Pure Python with no external dependencies.

**Tech:** Python, algorithms, Gale-Shapley, stable matching, combinatorial optimization, unittest

---

## 16. StreamFlow — Real-Time E-Commerce Data Pipeline

Production-style end-to-end streaming lakehouse pipeline. A Faker-based event generator produces 10+ events/second, ingested via Kafka into PySpark Structured Streaming, written to Delta Lake on S3 with exactly-once semantics, orchestrated by a 7-task Airflow DAG (hourly), transformed with dbt (staging + marts), and loaded into Google BigQuery. Full CI/CD via a 5-job GitHub Actions workflow (ruff, sqlfluff, dbt-parse, pytest, docker-compose validation), weekly CodeQL security scanning, Dependabot, and pre-commit hooks with gitleaks. Includes 4 Architecture Decision Records and a self-documenting Makefile.

**Tech:** Python, Apache Kafka, PySpark, Spark Structured Streaming, Delta Lake, AWS S3, Apache Airflow, dbt, Google BigQuery, Docker, GitHub Actions, CodeQL, CI/CD, pre-commit, pytest, ruff, sqlfluff, data engineering, streaming lakehouse
