# Get data collection by model name

```

const mongoose = require("mongoose");
mongoose.connect(process.env.MONGO_DB, { useNewUrlParser: true, useUnifiedTopology: true });

const connection = mongoose.connection;

connection.on('error', console.error.bind(console, 'connection error:'));
connection.once('open', async function () {

  const collection  = connection.db.collection("users")
  collection.find({}).toArray(function(err, data){
      console.log(data); // it will print your collection data
  });

});

```
