# REST API WITH PYTHON AND FLASK


## Abstract
This API provides a minimal endpoints for authentication and requests to performance the KD Rastreios app. The login is performed against the providers and returned as a JSON Web Token (JWT).
It can be used as:

* Standalone microservice
* Docker container

## Dependencies
* [Pyhton 3.8](https://www.python.org/downloads/release/python-380/)
* [Flask](https://flask.palletsprojects.com/en/1.1.x/)
* [Flask-JWT-Extended’s](https://flask-jwt-extended.readthedocs.io/en/stable/)
* [SQLAlchemy](https://docs.sqlalchemy.org/en/14/)
* [Gunicorn](https://docs.python-requests.org/en/master/) -used on deploy
* [Requests](https://docs.python-requests.org/en/master/) -used on deploy
  
  

## Setup
1. Make sure you have python version 3.8 or later 
2. Make sure you have and pip3 installed
3. Clone this repo into the folder of your choice
4. Create a virtual python environment
5. Run `pip install -r requirements.txt` to get all project dependencies
6. Clone [rest-api-kd-rastreios](https://github.com/lismaroliveira1/rest_api_KD_Rastreios.git) into a different directory
7. Run `python3 app.py` in terminal inside project folder
   


#### Possible Return Codes

| Code | Meaning               | Description                                                                                                               |
|------| ----------------------|---------------------------------------------------------------------------------------------------------------------------|
| 200  | OK                    | Successfully authenticated                                                                                                |
| 404  | Unauthorized          | The credentials are wrong                                                                                                 |
| 400  | Bad Request           | Missing parameters                                                                                                        |
| 500  | Internal Server Error | Internal error, e.g. the login provider is not available or failed                                                        |
| 303  | See Other             | Sets the JWT as a cookie, if the login succeeds and redirect to the URLs provided in `redirectSuccess` or `redirectError` |


## Rest Api 
-----

### Users Api

GET - getAll: [users/](http://localhost:5000/users)

GET - getById: [users/user_id](http://localhost:5000/users/user_id)

POST - updateUser: [user/user_id](http://localhost:5000/users/user_id) + include a json body with new user variables.

PUT - updateUser: [user/user_id](http://localhost:5000/users/user_id) + include a json body with new user variables.

DELETE - deleteUser: [user/user_id](http://localhost:5000/users/user_id)

### Packages - deployed on gcloud

GET - getAll: [packages/](http://localhost:5000/packages)

GET - getByPackageCode: [package/package_code](http://localhost:5000/package/package_code)  + include a json body with new package variables.

POST - newPackage: [package/package_code](http://localhost:5000/package/package_code)  + include a json body with new package variables.

PUT - updatePackage: [package/package_code](http://localhost:5000/package/package_code)  + include a json body with new package variables.

DELETE - deletePackage: [package/package_code](http://localhost:5000/package/package_code)


### Trackings

GET - getAll: [trackings/](http://localhost:5000/trackings)

GET - getByTrackingId: [tracking/tracking_id](http://localhost:5000/tracking/tracking_id)  + include a json body with new package variables.

POST - newTracking: [tracking/tracking_id](http://localhost:5000/tracking/tracking_id)  + include a json body with new package variables.

POST - updateTracking: [tracking/tracking_id](http://localhost:5000/tracking/tracking_id)  + include a json body with new package variables.

DELETE - deleteTracking: [tracking/tracking_id](http://localhost:5000/tracking/tracking_id)


Questions / Contact / Contribute
------------
Feel free to fork this repo, add to it, and create a pull request if you like to contribute.  

If you have any questions, you can contact me via email: `englismaroliveira@gmail.com`

## License

This project is licensed under the MIT License - see the [LICENSE.md] file for details
