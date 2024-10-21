# TP eval docker

# Sup de Vinci - Containers module project

*Tested with `rust v1.82.0` et `node 23.0.0`.*

## Development

### Basics

#### API

Use `cargo run` to start the dev environment.

You can also install [cargo-watch](https://crates.io/crates/cargo-watch) to watche over your project's source for changes, and runs Cargo commands when they occur : `cargo-watch -x run`.

#### Web

Use `npm install` to install all dependancies, and `npm run dev` to start the dev environment.

### Using Docker

1. Clonez ce repository :

    ```bash
    git clone https://github.com/Viveledelire/TP_eval_docker.git
    ```

2. Accédez au répertoire du projet :

    ```bash
    cd TP_eval_docker
    ```

3. Lancez les conteneurs en construisant les images :

    ```bash
    docker compose up --build
    ```

## Production

### Basics

#### API

Run `cargo build --release` to build and compile the app. This will create an executable in `/target/release/sdv-api`.

#### Web

Run `npm run build` to build the application, and run `npm run start` to start the Node.js server. 

### Using Docker

1. Dans le fichier `docker-compose.yaml` situé à la racine du projet, modifiez les sections build pour pointer vers les images Docker déjà construites, au lieu de spécifier un Dockerfile. Par exemple :

   ```yaml
   services:
     api:
       build:		         #
         context: .	         # Remplacez ceci par l'image appropriée
         dockerfile: Dockerfile  # 
   ```    
   ```yaml
   services:
     api:
       image: nom__image:tag  # Utilisez l'image Docker correspondante
   ```

2. Lancez les conteneurs :

   ```bash
   docker compose up
   ```

### Liens vers les images Docker

API : https://hub.docker.com/repository/docker/viveledelire/tp_eval_docker-api/general
Frontend : https://hub.docker.com/repository/docker/viveledelire/tp_eval_docker-web/general
