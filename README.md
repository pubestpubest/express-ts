# Express + TypeScript Project with pnpm

Follow these steps to set up a new project using **pnpm**, **Express**, and **TypeScript**.

---

## 1. Initialize the Project

Run the following command to create a `package.json` file:

```bash
pnpm init
```

## 2. Install Dependencies

Install the necessary dependencies using the following command:

```bash
pnpm add express
pnpm add -D typescript @types/node @types/express ts-node-dev
```

## 3. Create TypeScript Configuration

Generate a `tsconfig.json` file with the following command:

```bash
npx tsc --init
```

Update the tsconfig.json with the following settings:

```json
{
  "compilerOptions": {
    "target": "ES2020",
    "module": "CommonJS",
    "rootDir": "./src",
    "outDir": "./dist",
    "strict": true,
    "esModuleInterop": true,
    "skipLibCheck": true
  },
  "include": ["src/**/*.ts"],
  "exclude": ["node_modules"]
}
```

## 4. Create Project Structure

Create the following directories and files:

```bash
mkdir src
touch src/index.ts
```

## 5. Create a Basic Express Server

Create a `src/index.ts` file with the following content:

```ts
import express, { Request, Response } from "express";

const app = express();
const port = 3000;

app.get("/", (req: Request, res: Response) => {
  res.send("Hello, Express with TypeScript!");
});

app.listen(port, () => {
  console.log(`Server running at http://localhost:${port}`);
});
```

## 6. Add Scripts to package.json

Add the following scripts to the package.json file:

```json
"scripts": {
  "dev": "ts-node-dev --respawn --transpile-only src/index.ts",
  "build": "tsc",
  "start": "node dist/index.js"
}
```

## 7. Run the Server

To start the server in development mode, run:

```bash
pnpm run dev
```
