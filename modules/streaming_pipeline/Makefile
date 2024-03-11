# Export env variables from .env file if it exists.
ifneq (,$(wildcard .env))
include .env
export
endif

### Install ###

install:
	@echo "Installing streaming pipeline..."
	
	poetry env use $(shell which python3.10) && \
	PYTHON_KEYRING_BACKEND=keyring.backends.null.Keyring poetry install
