# Note-Mongoose


## Installation ////
/// create a folder //
 terminal >>>>> 
 ### 1. 
               npm i y 
### 2.
             npm install typescript --save-dev

### 3. 
            npm install express --save

### 4 . 
         npm install mongoose --save

 ### 5. 
        npm i ts-node-dev --save-dev
### 6 . /// in package.json////
         "start":"ts-node-dev --respawn --transpile-only src/server.ts",
### 8 . 
            
        async function main() {
        try {
            await mongoose.connect("mongodb://localhost:27017");
            console.log("SuccessFully connect mongodb".green.bold);
            app.listen(port, () => {
            console.log(`server listening on port ${port}`.green.underline.bold);
            });
        } catch (ConnectError) {
            console.log("failed to connect db", ConnectError);
        }
        }

        main();




### create app.ts  and exports  
        import express, { Application, NextFunction, Request, Response } from "express";
        import cors from "cors";

        const app: Application = express();

        app.use(cors());

        app.get("/", (req: Request, res: Response, next: NextFunction) => {
        res.send({ run: "success", message: "Server is running on 5000" });
        next();
        });

        export default app;

