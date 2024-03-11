# Streaming Pipeline

Real-time feature pipeline that:
- ingests current weather conditions from Accuweather [https://developer.accuweather.com/apis]
- cleans & transforms the weather documents into embeddings in real-time using [Bytewax](https://github.com/bytewax/bytewax?utm_source=thepauls&utm_medium=partner&utm_content=github)
- stores the embeddings into the [Qdrant Vector DB](https://qdrant.tech/?utm_source=thepauls&utm_medium=partner&utm_content=github)

The **streaming pipeline** is **automatically deployed** on an AWS EC2 machine using a CI/CD pipeline built in GitHub actions.


## Table of Contents

- [Streaming Pipeline](#streaming-pipeline)
  - [Table of Contents](#table-of-contents)
- [2. Install](#2-install)
  - [2.1. Dependencies](#21-dependencies)
  - [2.2. Accuweather and Qdrant](#22-accuweather-and-qdrant)
  - [2.3. AWS CLI](#23-aws-cli)
- [3. Usage](#3-usage)
  - [3.1. Local](#31-local)



# 2. Install

## 2.1. Dependencies

Main dependencies you have to install yourself:
* Python 3.10
* Poetry 1.5.1
* GNU Make 4.3
* AWS CLI 2.11.22

Installing all the other dependencies is as easy as running:
```shell
make install
```

When developing run:
```shell
make install_dev
```

Prepare credentials:
```shell
cp .env.example .env


## 2.2. Accuweather and Qdrant

## 2.3. AWS CLI
`deploy the streaming pipeline to AWS [optional]` 

You can deploy the streaming pipeline to AWS in 2 ways:
1. **running Make commands**: install & configure your [AWS CLI 2.11.22](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html) as explained in the [Setup External Services](https://github.com/iusztinpaul/hands-on-llms/tree/main#2-setup-external-services) section
2. **using the GitHub Actions CI/CD pipeline**: only create an account and generate a pair of credentials as explained in the [Setup External Services](https://github.com/iusztinpaul/hands-on-llms/tree/main#2-setup-external-services) section


# 3. Usage

## 3.1. Local

Run the streaming pipeline in `real-time` and `production` modes:
```shell
make run_real_time


run_real_time_dev:
	RUST_BACKTRACE=full poetry run python -m bytewax.run "tools.run_real_time:build_flow(debug=True)"




