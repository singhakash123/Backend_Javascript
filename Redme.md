                               - lecture 1 -

## node - v     to check the version of node  

## npm - v      to check version of node package manager

## type module use to make code asynchronous
         -- In a package.json file, "type": "module" specifies that the code in the project uses ECMAScript modules (ESM) syntax (e.g., import/export) instead of CommonJS.
## script : 
      "dev" : "node index.js"
       "dev" : "nodemon -r dotenv/config --exec node src/index.js"  
       
## npm and npm init :
        - npm : npm (Node Package Manager) is a tool that comes with Node.js, used for managing packages (libraries or modules) in JavaScript. It helps developers install, update, and manage dependencies for their projects efficiently.

 ## npm init : it is use to initlize node package manager 
        -npm init : npm init is a command used to create a new package.json file in a Node.js project. It initializes the project with metadata like name, version, description, and dependencies, helping manage the project efficiently.

## dependencies
       -- dependencies packages use for the production
       -- how to install dependencies
            -- npm install <pkg>

## devDependencies 
     - devDependencies packages  use at the time of development 
     - Dev dependencies are installed with the `-D` flag

     -- how to install devDependencies package 

      -- npm i -D <packagename>
           -- use capital letter of D to install devDependencies 

##  mkdir this command use to create folder
    -- use comma after every folder name (,)

##  touch this command use to create file
    -- use comma after every file name (,) 

## cd command use to go inside the file 
      exp : cd src   \\ now you will enter in the src folder

## cd.. // to come out from the file 
    exp:  cd.. // now you came out from src 

## How to configure git
    | git init    // you can initilize git for configration 
    | git add . // by using dot can be add all the file , if need to add solo file exp : index.js , then use git add index,js
    | git commit -m "message"  // by using this you can use custom commit message 
    | git branch -m "main"  // you can set branch name 
    | git remote add origan // this is git repositartu url 
    | git push -u  origan main

     // note : git track only files not folder    
     // git status use to check track 
     // .gitkeep  , it is use to keep empty folder in the git so that git can track empty folder 

## mrkdown 
   ## inside the src folder
``
 
src 
    | - index.js (this file is use to connect database)
    | - app.js ()
    | - constant.js

    | - models : exp -
                            | - user.model.js
                            | - product.model.js

    | - controllers : exp - 
                            |- user.controllers.js
                            |- product.controllers.js

    | - routes : exp - 
                            |- user.route.js 
                            |- product.route.js

    | - middlewares : exp -
                            |- user.middleware.js
                            |- product.middleware.js

                        
    | - utils :  exp-
                           |- utils.js


    | - db   
``
  ## outside of src 
```
.env || this should be config in the entry file 
.env.sample || to give the sample of env variable
.prettierrc (https://michelelarson.com/prettier-config/)
.prettierigore(use generator)
.gitignore (https://mrkandreev.name/snippets/gitignore-generator/)
public/temp .gitkeep

```





                                           --  NODEMON  --

##  nodemon  config 

    [-- Syntax : 
              "dev": "nodemon -r dotenv/config --exec node src/index.js"
              ] 
--     -- nodemon: Watches for changes and restarts the server automatically.
--     -- -r dotenv/config: Preloads environment variables from a .env file before running   the script
--     -- exec node, ensuring Nodemon runs the script explicitly with Node.js.
--     -- src/index.js: The entry point of your application  
--     -- whenever change in dotenv file then stop and start because nodemon doesnt restart changing in the dotenv file 

--      nodemon is a devDependencies  it use at the time of developmenet 




                                                          -- dotenv config -- 

##  dotenv config 
  -- configration of  dotenv  should be  in the main entry file
import dotenv from "dotenv"
dotenv.config({
    path : "./.env"
})

   -- to access dotenv variable use [process.env.variable_Name]



                                                -- prettierrc --

## perttirc is also devDependencies 
##  prettierrc 
```
           [
-- "semi": true
     -- This means that Prettier will automatically add a semicolon (;) at the end of statements. For example, const a = 10;.

-- "singleQuote": true
     -- Strings will be wrapped in single quotes (') rather than double quotes ("). For example, 'Hello World' instead of "Hello World".

-- "tabWidth": 2
    -- Defines the number of spaces per indentation level. In this case, each indentation will be 2 spaces.

-- "trailingComma": "all"
   -- Ensures that trailing commas are added wherever possible, including in function parameters and lists. For example:
const array = [1, 2,3,];

-- "printWidth": 100
   -- Specifies the line length that Prettier will wrap lines at. If a line exceeds 100 characters, Prettier will break it into multiple lines.

-- "bracketSpacing": true
   -- This option adds spaces between brackets in object literals. For example, { foo: bar } rather than {foo: bar}.

-- "arrowParens": "always"
This forces parentheses around the parameters of arrow functions, even if there's only one parameter. For example:
const sum = (a, b) => a + b;
rather than const sum = a => a + b;.


-- "endOfLine": "lf"
 -- This sets the line endings to LF (Line Feed), which is the Unix-style line ending. It ensures consistency for line breaks.

-- "jsxSingleQuote": false
  -- For JSX files, this ensures that double quotes are used for attributes instead of single quotes. For example, <div className="container"> instead of <div className='container'>.

-- "proseWrap": "preserve"
    -- This option controls how markdown text is wrapped. If set to "preserve", Prettier will leave the markdown wrapping as is, without altering it.
            
            ]                      


         {
  "semi": true,
  "singleQuote": true,
  "tabWidth": 2,
  "trailingComma": "all",
  "printWidth": 100,
  "bracketSpacing": true,
  "arrowParens": "always",
  "endOfLine": "lf",
  "jsxSingleQuote": false,
  "proseWrap": "preserve"
}
```    

## now without installing nodemon can be config 
      ## node --watch <enter file path>

## http://localhost:<port>
## to read api use (json formatter )

## mongoose and express use in the backend 




                                               - lecture 2 : 
                        
## mongoose is use to connect db and to make schema 
## database is always in another contenet so always  use async await 
## database can create problem so  always use  try catch 
## if the file is js then always use dot js extension at the time of import 

##  process.exit() is used to terminate a running process explicitly. It accepts an optional exit code (e.g., 0 for success, or 1 for failure) to indicate the reason for the exit. Using it abruptly stops the event loop, skipping cleanup tasks like closing database connections.

 
                               -- mongodb - connection - uri --

##  mongodb_URI
   ## to get the MongoDB Atlas connection string, follow these steps:

-- 1st step 
          -- Create a Cluster: 
                    --  go to the Clusters tab.
                    -- Click on Build a Cluster and choose your desired configuration (Cloud Provider, Region, Cluster Tier).
                    -- Click Create Cluster. It may take a few minutes to set up.

-- 2nd step 
          -- Create a Database User:
                    --  After the cluster is ready, go to the Database Access tab.
                    --  Click Add New Database User.
                    --  Set a username and password (make sure to note these down as you'll need them for the connection string)
                    --  Assign appropriate permissions (e.g., read and write access to all databases or specific databases).
                    --  Click Add User.
        note : while making password remember password special character can create problem 

-- 3rd step 
          -- Whitelisted IP Address:
                    -- Go to the Network Access tab.
                    -- Click Add IP Address.
                    -- Either add a specific IP or click Allow Access from Anywhere (0.0.0.0/0) for broader access.
                    -- Click Confirm.

-- 4th step 
          -- Get the Connection String:
          -- Go to the Clusters tab and click Connect.
          -- Choose Connect your application.
          -- You will see a connection string in the format
                      - mongodb+srv://<username>:<password>@cluster0.mongodb.net/myFirstDatabase?retryWrites=true&w=majority
          -- Replace <username> and <password> with the database username and password you created earlier.
          -- Optionally, replace myFirstDatabase with the name of the database you want to connect to.





                                        -- lecture 3 -
## custom api error and response 

                                    -- customApiError --
##  custom api error 

class ApiError extends Error {
    constructor(
        statusCode,
        message = "something went wrong",
        errors = [],
        stack = "",
        data = null  // Add 'data' as a parameter
        success = false 
    ) {
        super(message);
        this.statusCode = statusCode;
        this.message = message;
        this.success = success
        this.errors = errors;
        this.data = data;

        if (stack) {
            this.stack = stack;
        } else {
            Error.captureStackTrace(this, this.constructor);
        }
    }
}

export { ApiError };


                               - customApi response --

##  custom api response
class ApiResponse {
    constructor(statusCode, data, message = "Success"){
        this.statusCode = statusCode
        this.data = data
        this.message = message
        this.success = statusCode < 400
    }
}

export { ApiResponse }                        


                                       -- lecture 4 --

## mongoose use for the data modeling                                       

## model file name : 
       - user.model.js

## data modeling step : 

  ## 1 . imort mongoose : 
      --  import mongoose ,{schema} from "mongoose"

  ## 2 . Define a Schema
     -- const userSchema = new Schema (
           {
            name : {
                  type : String  , 
                  required : true , 
                  index : true , 
            }  , 
            subUser : {
                   type : Schema.Type.ObjectId , 
                   ref  : // Matches the model name registered in Mongoose
            }  // not need to import 
          } ,
        {
        timestamps : true
        })
            : timestamps is used to add created at and updated at fields in the database
            ## // 🔹 **Indexing for performance**
            : refrence is used to make a relation with another model in the database
                  : ref is used to define the name of the model that we are referencing in the 
                  : mongoose.Schema.Types.ObjectId is used to define the type of the field in the databas
                  : type is used to define the type of the field in the database

// same name can be in a different models 

  ## 3 . Create a Model
     --export const User = mongoose.model("User" ,userSchema )
                               -- : User will become users in the databasr // it will be in a small letter plus it will become plural 





                                   -----bcrypt js -------
                                   

## bcrypt js 
  -- Bcrypt.js is a library that helps you hash passwords securely and verify them. It’s useful when you need to store passwords in a secure way, as hashing makes it hard for someone to retrieve the original password, even if they have access to the stored data.
       --  Syntax and Use Cases for bcrypt.js
                --  First, you'll need to install the package:
                               --  npm install bcryptjs
-- 1    Hashing a Password:
-- saltRounds: The higher the number, the more secure the hash (and slower to generate). Typically, you would use a value like 10 or 12.
-- hash(): The hash function takes the password and salt rounds, and returns a hashed password.

-- 2    Comparing Hashed Password with Input: 


## bcrypt -- hashing 
         // 🔒 hash password before saving : 
userSchema.pre("save", async function (next) {
  if(!this.isModified("password")) return next()
       try{
                 const salt = await bcrypt.genSalt(10) 
                 this.password = await bcrypt.hash(this.password, salt) 
                  next();
       }catch(error){
          next(error)
       }
} )


## compare password 
userSchema.methods.comaprePassword = async function (enterdPasswrd) {
         try{
           return await bcrypt.hash(enterdPasswrd , this.password)
         }catch(error){
                  console.log('error comapring password' , error)
                  return false 
         }
}


                                     --- Jwt ---


## jwt token generate 
userSchema.methods.generateAccessToken =  function () {
          try{
               return jwt.sign(
                  {
                        id:this._id,
                        role:this.role
                  },
                  process.env.Secret_key ,
                   {expiresIn : "7d"})
          }catch(error){
                  console.error("JWT Generation Error:", error.message); 
                  throw new Error("Failed to generate access token")
          }
}
/*
What is the throw Keyword in JavaScript?
The throw keyword is used to manually trigger (throw) an error in JavaScript. It stops the execution of the current function and passes the error to the nearest catch block or error handler.


                                       --- virtual --


## virtual 
userSchema.virtual("maskedEmail").get( function () {
       const part = this.email.split('@')
       return part[0].subString(0,3) + "****@" + part[1]
})

userSchema.virtual('maskedMobileNumber').get(function () {
          return this.mobile.subString(0,3) + "*****" + this.mobile.subString(7)
})

// Virtuals are computed properties that are not stored in the database but are derived from existing fields.
// This virtual property creates a masked version of a user's email, hiding part of the local part (before @) for privacy and security.



                                    ---  soft delete ---




## soft delete config 
userSchema.methods.softDelet = function () {
       this.deleted = true , 
       this.deletedAt = new Date().toLocaleString()
       return this.save()
}


1. User Accounts
Use Case: When a user deletes their account or when their account is deactivated, instead of permanently removing the record from the database, you could set a deleted flag or deletedAt timestamp.
Why: This allows you to retain the account for audit purposes (e.g., who deleted it and when) or for data recovery in case the deletion was accidental.

productSchema.methods.softDelet = function () {
        this.dicontinued = true , 
        this.dicontinuedAt = new Date().toLocaleDateString()
}

2. Products or Items in an E-commerce Platform
Use Case: When a product is no longer available or is removed from the storefront, rather than deleting the product entirely from the database, you can mark it as "discontinued" or "out of stock."
Why: This allows for tracking the historical availability of the product and maintaining accurate inventory and transaction data.





                                             -- lecture 5 --

## file upload by multer 








                                             -- lecture 6 -- 
## http crash course 

## These are HTTP methods (GET, POST, PUT, DELETE),define the type of action a client wants to perform when making a request to the server

    GET: Retrieves data from the server without modifying it.
    POST: Sends data to the server to create a new resource.
    PUT: Updates an existing resource on the server with new data.
    DELETE: Removes a resource from the server.


                                             -- lecture 7 ---
## router setting  and controller 


                                            -- lecture 8 --
## logic building key point 

                                        
                                             -- lecture 9 --  
## how to use postman 

                                  
                                             -- lecture 10 --
                                        
## token  ,   midlleware   , cookies 


                                            -- lecture 11 --

## 