.PHONY: install test format lint all

# Default Python command
PYTHON = python3
PIP = pip

install:
	$(PIP) install --upgrade pip
	$(PIP) install -r requirements.txt

install-dev: install
	$(PIP) install pytest pylint black pytest-cov

test:
	pytest -v --cov=.

test-hello:
	pytest -vv test_hello.py

format:
	black *.py

lint:
	pylint --disable=R,C,W1203 *.py || true  # Don't fail on linting

all: install-dev lint test