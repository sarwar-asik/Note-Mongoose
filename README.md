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
        } catch (ConnectError) {
            console.log("failed to connect db", ConnectError);
        }
     }
