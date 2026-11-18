# Daylight

A lightweight task-list web app. Add, complete, filter, and delete tasks; your list is saved in the browser's local storage.

## Run locally

Open `index.html` in a browser. The app has no build step or package dependencies.

## Run with Docker

Install and start Docker Desktop, wait until it reports that the engine is running, then run these commands from the project directory:

```powershell
docker build -t daylight-app .
docker run --name daylight-app -d -p 8081:80 daylight-app
```

Open <http://localhost:8081>. The host port is `8081` because `8080` is already in use on the development machine. If `8081` is busy on your computer, replace the number before `:80` with another available port.

To stop and remove the container:

```powershell
docker stop daylight-app
docker rm daylight-app
```

To rebuild after changing the source, remove the old container, rebuild the image, and start it again:

```powershell
docker stop daylight-app
docker rm daylight-app
docker build -t daylight-app .
docker run --name daylight-app -d -p 8081:80 daylight-app
```

## Publish the source to GitHub

1. Install Git and create or sign in to a GitHub account.
2. On GitHub, create a **new empty repository** (for example, `daylight-app`). Do not initialize it with a README or other files.
3. Configure the author details Git will use for your commits:

   ```powershell
   git config --global user.name "Your Name"
   git config --global user.email "you@example.com"
   ```

4. In PowerShell, from this project directory, initialize Git and push the source. Replace the URL with the HTTPS URL for your repository:

   ```powershell
   git init
   git add .
   git commit -m "Create Daylight task app"
   git branch -M main
   git remote add origin https://github.com/YOUR-USERNAME/daylight-app.git
   git push -u origin main
   ```

5. When you make future changes, save and upload them with:

   ```powershell
   git add .
   git commit -m "Describe your change"
   git push
   ```

Use the email you want associated with your GitHub commits, and authenticate to GitHub when prompted. The Docker image built above is local to your computer; publishing an image to a registry such as GitHub Container Registry is a separate optional step.
