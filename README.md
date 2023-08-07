// app.js
const express = require('express');
const bodyParser = require('body-parser');
const app = express();

app.use(bodyParser.json());


app.post('/generate-response', (req, res) => {

  const { username, email, password, full_name, age, gender } = req.body;

  
  const responseObject = {
    username: username,
    email: email,
    password: password,
    full_name: full_name,
    age: age,
    gender: gender,
  };

  res.json(responseObject);
});


const PORT = process.env.PORT || 3000;
app.listen(PORT, () => {
  console.log(`Server started on port ${PORT}`);
});
