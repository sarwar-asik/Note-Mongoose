## Update operator

### $set :

### addToSet (update a element of array without replacing)

        db.practice3.updateOne(
        {_id:ObjectId('64634040e5044eef0fa0d60e')},
        {$addToSet:{
                interests:{$each:["Cooking"]}
        }},
        {upsert:true}
        )

### unset (delete a property or filed in data)

        db.practice3.updateOne(
    {_id:ObjectId("64634047e5044eef0fa0d60f")},
    {
        $unset: {occupation: "" }
    }
    )

### pop (delete last data(1) or first data (1) from a field)

            db.practice3.updateOne(
    {_id:ObjectId("64634047e5044eef0fa0d60f")},
    {
        $pop: {friends:1 }
    }
    )

    output :::  "friends" : [ "Fahim Ahammed Firoz", "Najmus Sakib", "Rasel Ahmed" ],

### pull (delete definite data from a field)

        db.practice3.updateOne(
            {_id:ObjectId("64634047e5044eef0fa0d60f")},
            {
                $pull: {friends:"Najmus Sakib" }
            }
            )

     output ::::   "friends" : [ "Fahim Ahammed Firoz",  "Rasel Ahmed" ],

### pullAll (delete multiple data from a field)

        db.practice3.updateOne(
            {_id:ObjectId("64634047e5044eef0fa0d60f")},
            {
                $pullAll: {friends:["Robi","Saju"]}
            }
            )

     output ::::   "friends" : [ "Fahim Ahammed Firoz",  "Rasel Ahmed" ],

### inc (add or plus or increment data )

        db.practice3.updateOne(
    {_id:ObjectId('64634047e5044eef0fa0d60f')},
    {
        $inc: {age:10}
    }
    )

### rename (rename a field name)

        db.practice3.updateMany(
    {},
    {
        $rename: {"favoutiteColor":"favouriteColor"}
    }
    )
