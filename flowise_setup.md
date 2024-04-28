# Prompt-Engineering---Final-Project
What is Flowise?
Flowise is an open-source, low-code platform designed to help developers create customized large language model (LLM) applications. It features a drag-and-drop interface that simplifies the process of building and customizing LLM flows and AI agents, making it accessible for both programmers and non-programmers alike. Users can utilize built-in app templates for various functions, including conversational agents that can interact with PDFs and Excel files. Flowise supports deployment on multiple cloud platforms and can run in air-gapped environments with local LLMs and vector databases​.
**Flowise Documentation** URL:- https://docs.flowiseai.com/
# Prequisites:
-  Latest NodeJS installed
-  Docker (optional) recommended when want to launch flowise using Docker otherwise not Required
-  openAI_API_key
-  Pinecone_API_KEY(when using Vector DB to chat with your own data)
# Three Ways to launch/install Flowise on your Local
YOUTUBE TUTORIAL LINKS
1.https://www.youtube.com/watch?v=nqAK_L66sIQ&list=PL4HikwTaYE0H7wBxhvQqxYcKOkZ4O3zXh&ab_channel=LeonvanZyl
2.https://www.youtube.com/watch?v=kAyKOsm8L5Y&list=PL4HikwTaYE0H7wBxhvQqxYcKOkZ4O3zXh&index=2&ab_channel=LeonvanZyl
3.https://www.youtube.com/watch?v=yLfiNnK4NOM&list=PL4HikwTaYE0H7wBxhvQqxYcKOkZ4O3zXh&index=3&ab_channel=LeonvanZyl
4.https://www.youtube.com/watch?v=bT308854-Qw&list=PL4HikwTaYE0H7wBxhvQqxYcKOkZ4O3zXh&index=4&ab_channel=LeonvanZyl

**QUICKSTART**
Navigate to Terminal or command prompt
1. install flowise
Run this command: npm install -g flowise
2. Start Flowise
Run this command: npx flowise start
3. Open http://localhost:3000
**DOCKER**

1.Go to docker folder at the root of the project

2.Copy the .env.example file and paste it as another file named .env

3.docker-compose up -d

4.Open http://localhost:3000

5.You can bring the containers down by docker-compose stop

**Docker Image**
1.Build the image locally:

Copy
docker build --no-cache -t flowise .
2.Run image:

Copy
docker run -d --name flowise -p 3000:3000 flowise
3.Stop image:

Copy
docker stop flowise
**Flowise has 3 different modules in a single mono repository.**

server: Node backend to serve API logics

ui: React frontend

components: Integrations components

**Prerequisite**
Install PNPM

Copy
npm i -g pnpm
**Setup**
1. Clone the repository
Copy
git clone https://github.com/FlowiseAI/Flowise.git

2. Go into repository folder
Copy
cd Flowise

3. Install all dependencies of all modules:
Copy
pnpm install

4. Build all the code:

Copy
pnpm build

5. Start the app:
Copy
pnpm start

You can now access the app on http://localhost:3000

6. For development build:

Create .env file and specify the PORT (refer to .env.example) in packages/ui

Create .env file and specify the PORT (refer to .env.example) in packages/server

Copy
pnpm dev
Any code changes will reload the app automatically on http://localhost:8080
