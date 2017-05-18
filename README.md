# ![cf](https://i.imgur.com/7v5ASc8.png) Rest Insured

[![Coverage Status](https://coveralls.io/repos/github/MoneyCashNodes/RestInsured-API/badge.svg?branch=master)](https://coveralls.io/github/MoneyCashNodes/RestInsured-API?branch=master)
[![Build Status](https://travis-ci.org/MoneyCashNodes/RestInsured-API.svg?branch=master)](https://travis-ci.org/MoneyCashNodes/RestInsured-API)

Team Name: MoneyCacheNodes

Abigail White | Ben Ayzenberg | Enrique Rico | Kayla Asay
:----------------------------:|:----------------------------: | :------:| :------:
[![Abigail White](image)](https://github.com/abswhite) | [![Ben Ayzenberg](image)](https://github.com/luayyounus) | [![Enrique Rico](image)](https://github.com/EnriqueRico)[![Kayla Asay ](image)](https://github.com/thegrimheep)

## Project Concept:
* Connect users with medical facilities that accept their insurance, based on user input of location and insurance provider.
* Utilize registered user functionality to access app functionality

This app is intended for educational purposes only. This project does not maintain user medical records with respect to health care needs or preferences. This app does not persist records of previous health care appointments or illness.

## Summary
### MVP
* Registered user takes in full name, email, location, provider, password info
  * Input of provider info and location
  * User location
  * Range of query
  * Insurance provider name
* Output of medical institutions (dental, pharmacy, doctors) that accept insurance.
  * Visualization: interactive pins on a map AND listed information beneath map
* Provided info includes:
  * Doctor
  * Phone number
  * Name
  * Practice
  * Practice name
  * Insurance providers accepted (list)
  * Practice phone number
  * Specialty
  * Location

### Future Opportunities
* Filter requests to api by “specialty”
* Book appointments functionality
* Calendar notifications of appointment
* Unregistered user functionality to access query and map functionality

### Resources
  * BetterDoctor API: Retrieve insurance information
  * Mongo DataBase: Maintain user registration data
  * Heroku deployment
  * Express: Node.js Web Apps
  * Mongoose: Manage asynchronous environment
  * JSON web token
  * Bluebird: Promise rendering
  * Body parser: Middleware development
  * Debug: Debugging code process
  * Cors: Provides Express middleware

  * Developer only:
      * Mocha: Testing
      * Chai: Testing assertions
      * Chai-http: Testing with local server environment

#### Team Collaboration Tools
  * GitHub Projects/ Organization
  * Google Docs for larger overview, daily stand-ups
  * Slack for basic communication
_____
## API Endpoints
Deployed endpoint: `https://rest-insured-production.herokuapp.com`

### Create and Modify User
1. Create Account: `https://rest-insured-production.herokuapp.com/signup <fullName>=<input> <email>=<input> <password>=<input> <insurance>=<input>`
2. Fetch Account: `https://rest-insured-production.herokuapp.com/signin -a <email>:<password>`
3. Update Account: `https://rest-insured-production.herokuapp.com/update/<user id> <key>:<changed value> 'Authorization:Bearer <token>'`
4. Delete Account: `https://rest-insured-production.herokuapp.com/delete/<user id> 'Authorization:Bearer <token>'`

### Doctor and Practice Retrieval
Utilize `http://api.betterdoctor.com` as basis for request endpoints.
Further documentation found at [Better Doctor API:](https://developer.betterdoctor.com/documentation15)

1. Fetch provider information based on Location and Insurance Provider input.

API URL Request:
`https://api.betterdoctor.com/${date}/doctors?insurance_uid=${req.query.insurance}&location=${req.query.lat}%2C${req.query.lon}%2C${req.query.range}&limit=5&user_key=${process.env.user_key}`

#### Sample JSON
Example of data output from API request
```
{
  "Providers": [
    {
      "Practice" : {
        "Name" : "Good Doctors",
        "phone" : "1111111111",
        "uid" : "1234uiid576851234",
        "lat" : 47.635867,
        "long" : -122.281694,
        "state": "WA",
        "state_long": "Washington",
        "street": "821 Saint Helena Hwy S",
        "zip": "98116",
        "accepts_new_patients": true,
        "Doctors" : [
          {
            "Doctor Name" : "Adam Scott",
            "Specialty" : "cardiologist"
          }
        ]
      }
    }
  ]
}
```
### License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details

### Acknowledgments

Thank you to Adam Wallraff, Scott Schmidt, Thomas Martinez, Devon Hackley for guidance and assistance throughout the project.
