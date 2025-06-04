# 🐳 Dockerfile Optimization

This project demonstrates an evolving series of Dockerfiles designed to apply **Docker best practices**, with a focus on:

- Reducing image size
- Improving build efficiency
- Using multi-stage builds
- Separating concerns (build vs runtime)
- Optimizing for production

## 🧱 Dockerfile Versions

| Version | Improvements Introduced                                                       |
|---------|--------------------------------------------------------------------------------|
| v1      | Basic Node-based build                                                        |
| v2      | Using lightweight Alpine image                                                |
| v3      | Multi-stage build                                                             |
| v4      | Production build with static output only                                      |
| v5      | Alpine-based Node & Nginx build to reduce size and serve static files         |

Each Dockerfile is named like: `dockerfile.v1`, `dockerfile.v2`, ..., `dockerfile.v5`.

## 📦 Docker Image Size Comparison

![image-size-comparison](./image-size-comparison.png)

## 🚀 Building the Images

Navigate to the `react-app` directory and build a specific version using:

```bash
cd react-app
````

Example:

```bash
docker build -f ../Dockerfiles/dockerfile.v5 -t react-demo:v5 .
```

## ▶️ Running the Containers

```bash
# Run version 5
docker run -p 80:80 -d react-demo:v5 

# Run version 4
docker run -p 3000:3000 -d react-demo:v4

# Run version 1 to 3 (uses Vite dev server)
docker run -p 5173:5173 -d react-demo:v3
```

Check running containers:

```bash
docker ps
```

Visit the respective ports in your browser to verify the application is running.

---
