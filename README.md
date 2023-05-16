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
            app.use(express.json())
            app.use(express.urlencoded({extended:true}))

        app.get("/", (req: Request, res: Response, next: NextFunction) => {
        res.send({ run: "success", message: "Server is running on 5000" });
        next();
        });

        export default app;

### start crud ///




## Update operator
###   $set   :

### addToSet (update a element of array without replacing) 
        db.practice3.updateOne(
        {_id:ObjectId('64634040e5044eef0fa0d60e')},
        {$addToSet:{
                interests:{$each:["Cooking"]}
        }},
        {upsert:true}
        )
### unset  (delete a property or filed in data)

        db.practice3.updateOne(
    {_id:ObjectId("64634047e5044eef0fa0d60f")},
    {
        $unset: {occupation: "" }
    }
    )
### pop (delete last data from a field) 

            db.practice3.updateOne(
    {_id:ObjectId("64634047e5044eef0fa0d60f")},
    {
        $pop: {friends:1 }
    }
    )

    output :::  "friends" : [ "Fahim Ahammed Firoz", "Najmus Sakib", "Rasel Ahmed" ],