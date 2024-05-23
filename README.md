# Rock-Paper-Scissors Game on AWS ✊📃✂️

Welcome to our cloud-based Rock-Paper-Scissors game! Here, you can join a public lobby, set up a private game, or challenge your friends. It's all deployed on AWS using ECS for a scalable and reliable experience.

## Features

- **Public Lobby**: Jump into a game with random players from around the world.
- **Private Lobby**: Create or join a private game with a unique code.
- **Friend Matches**: Challenge your friends to a game.
- **Responsive Design**: Enjoy the game on both desktop and mobile devices.

## Tech Stack

- **Frontend**: Built with [React](https://reactjs.org/) (or your preferred framework).
- **Backend**: Powered by [Node.js](https://nodejs.org/) and [Express](https://expressjs.com/).
- **Database**: Data is stored using [Amazon RDS](https://aws.amazon.com/rds/).
- **Containerization**: Everything is containerized with Docker.
- **Deployment**: Hosted on AWS ECS (Elastic Container Service) with Fargate.

## Prerequisites

Before you start, make sure you have:

- [Node.js](https://nodejs.org/) installed.
- [Docker](https://www.docker.com/) up and running.
- An [AWS account](https://aws.amazon.com/).
- AWS CLI configured with your credentials.
- [Terraform](https://www.terraform.io/) if you're using Infrastructure as Code (optional).

## Getting Started

### Frontend

1. Navigate to the `frontend` directory:
    ```bash
    cd frontend
    ```

2. Install all the dependencies:
    ```bash
    npm install
    ```

3. Start the development server:
    ```bash
    npm start
    ```

### Backend

1. Head over to the `backend` directory:
    ```bash
    cd backend
    ```

2. Install the necessary packages:
    ```bash
    npm install
    ```

3. Fire up the development server:
    ```bash
    npm start
    ```

## Deployment

### Docker

1. Build Docker images for both the frontend and backend:
    ```bash
    cd frontend
    docker build -t your-ecr-repo/frontend .

    cd ../backend
    docker build -t your-ecr-repo/backend .
    ```

2. Push these images to Amazon ECR:
    ```bash
    aws ecr get-login-password --region your-region | docker login --username AWS --password-stdin your-account-id.dkr.ecr.your-region.amazonaws.com
    docker push your-account-id.dkr.ecr.your-region.amazonaws.com/frontend
    docker push your-account-id.dkr.ecr.your-region.amazonaws.com/backend
    ```

### AWS ECS

1. Set up an ECS cluster and define tasks for the frontend and backend.
2. Create services for each task within the ECS cluster.
3. Configure an Application Load Balancer (ALB) to route traffic to your ECS services.

## Environment Variables

Make sure you have the following environment variables set for the backend:

- `DB_HOST`: Your database host.
- `DB_USER`: Your database username.
- `DB_PASSWORD`: Your database password.

## CI/CD Pipeline

For seamless deployments, set up a CI/CD pipeline using AWS CodePipeline, CodeBuild, and CodeDeploy.

## Monitoring and Logging

Keep an eye on your application with AWS CloudWatch for logging and monitoring.

## License

This project is open-sourced under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Contributing

We welcome contributions! Feel free to open an issue or submit a pull request.

## Contact

Have questions or need help? Reach out to us at [your-email@example.com](mailto:your-email@example.com).
