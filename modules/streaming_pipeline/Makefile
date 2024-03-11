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

install_dev: install
	PYTHON_KEYRING_BACKEND=keyring.backends.null.Keyring poetry install --with dev

install_only_dev:
	PYTHON_KEYRING_BACKEND=keyring.backends.null.Keyring poetry install --only dev


### Run ###

run_real_time:
	RUST_BACKTRACE=full poetry run python -m bytewax.run tools.run_real_time:build_flow

run_real_time_dev:
	RUST_BACKTRACE=full poetry run python -m bytewax.run "tools.run_real_time:build_flow(debug=True)"
