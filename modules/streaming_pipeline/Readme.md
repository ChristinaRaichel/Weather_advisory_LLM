# Streaming Pipeline

Real-time feature pipeline that:
- ingests current weather conditions from Accuweather [https://developer.accuweather.com/apis]
- cleans & transforms the weather documents into embeddings in real-time using [Bytewax](https://github.com/bytewax/bytewax?utm_source=thepauls&utm_medium=partner&utm_content=github)
- stores the embeddings into the [Qdrant Vector DB](https://qdrant.tech/?utm_source=thepauls&utm_medium=partner&utm_content=github)

The **streaming pipeline** is **automatically deployed** on an AWS EC2 machine using a CI/CD pipeline built in GitHub actions.


## Table of Contents

- [1. Motivation](#1-motivation)
- [2. Install](#2-install)
    - [2.1 Dependencies](#21-dependencies)
    - [2.2. Alpaca & Qdrant](#22-alpaca--qdrant)
    - [2.3. AWS CLI](#23-aws-cli)
- [3. Usage](#3-usage)
    - [3.1. Local](#31-local)
    - [3.2. Docker](#32-docker)
    - [3.3. Deploy to AWS](#33-deploy-to-aws)
    - [3.4. Linting & Formatting](#34-linting--formatting)

