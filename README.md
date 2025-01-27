# Dockerfile Bug: Missing Working Directory
This repository demonstrates a common Dockerfile error: not specifying a working directory.  The provided Dockerfile attempts to run a Python application, but it fails because the application cannot find its dependencies or files. The solution shows how to correctly specify a working directory to resolve the problem.

## Bug
The original `Dockerfile` lacks a `WORKDIR` instruction. This causes the application to run in the root directory of the container, leading to errors if the application relies on relative paths.

## Solution
The `Dockerfile_solution.txt` adds a `WORKDIR` instruction to set the working directory to `/app`. This ensures that the application and its dependencies are in the correct location within the container. The `COPY` instruction then places the application files into `/app`.