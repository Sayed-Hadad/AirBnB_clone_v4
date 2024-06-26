# <span style="color:red">_AirBnB clone - Web dynamic_</span>

The console is the first segment of the AirBnB project at Holberton School that collectively covers fundamental concepts of higher-level programming. The goal of the AirBnB project is to eventually deploy our server, a simple copy of the AirBnB Website (HBnB). A command interpreter is created in this segment to manage objects for the AirBnB (HBnB) website.

## <span style="color:red">_Functionalities of this command interpreter:_</span>
* Create a new object (e.g., a new User or a new Place)
* Retrieve an object from a file, a database, etc...
* Perform operations on objects (count, compute stats, etc...)
* Update attributes of an object
* Destroy an object

## <span style="color:red">_Table of Contents_</span>
* [<span style="color:red">_Environment_</span>](#environment)
* [<span style="color:red">_Installation_</span>](#installation)
* [<span style="color:red">_File Descriptions_</span>](#file-descriptions)
* [<span style="color:red">_Usage_</span>](#usage)
* [<span style="color:red">_Examples of Use_</span>](#examples-of-use)
* [<span style="color:red">_Bugs_</span>](#bugs)
* [<span style="color:red">_Authors_</span>](#authors)
* [<span style="color:red">_License_</span>](#license)

## <span style="color:red">_Environment_</span>
This project is interpreted/tested on Ubuntu 14.04 LTS using Python 3 (version 3.4.3).

## <span style="color:red">_Installation_</span>
* Clone this repository: `git clone "https://github.com/alexaorrico/AirBnB_clone.git"`
* Access the AirBnb directory: `cd AirBnB_clone`
* Run hbnb (interactively): `./console` and enter a command
* Run hbnb (non-interactively): `echo "<command>" | ./console.py`

## <span style="color:red">_File Descriptions_</span>
- [console.py](console.py) - the console contains the entry point of the command interpreter.
  List of commands this console currently supports:
  * `EOF` - exits the console
  * `quit` - exits the console
  * `<emptyline>` - overwrites the default empty line method and does nothing
  * `create` - Creates a new instance of `BaseModel`, saves it (to the JSON file), and prints the id
  * `destroy` - Deletes an instance based on the class name and id (save the change into the JSON file).
  * `show` - Prints the string representation of an instance based on the class name and id.
  * `all` - Prints all string representation of all instances based or not on the class name.
  * `update` - Updates an instance based on the class name and id by adding or updating attribute (save the change into the JSON file).

- `/models/` directory contains classes used for this project:
  - [base_model.py](/models/base_model.py) - The BaseModel class from which future classes will be derived
    * `def __init__(self, *args, **kwargs)` - Initialization of the base model
    * `def __str__(self)` - String representation of the BaseModel class
    * `def save(self)` - Updates the attribute `updated_at` with the current datetime
    * `def to_dict(self)` - returns a dictionary containing all keys/values of the instance

  Classes inherited from Base Model:
  - [amenity.py](/models/amenity.py)
  - [city.py](/models/city.py)
  - [place.py](/models/place.py)
  - [review.py](/models/review.py)
  - [state.py](/models/state.py)
  - [user.py](/models/user.py)

- `/models/engine` directory contains the File Storage class that handles JSON serialization and deserialization:
  - [file_storage.py](/models/engine/file_storage.py) - serializes instances to a JSON file & deserializes back to instances
    * `def all(self)` - returns the dictionary __objects
    * `def new(self, obj)` - sets in __objects the obj with key <obj class name>.id
    * `def save(self)` - serializes __objects to the JSON file (path: __file_path)
    * `def reload(self)` - deserializes the JSON file to __objects

- `/tests` directory contains all unit test cases for this project:
  - [/test_models/test_base_model.py](/tests/test_models/test_base_model.py)
  - [/test_models/test_amenity.py](/tests/test_models/test_amenity.py)
  - [/test_models/test_city.py](/tests/test_models/test_city.py)
  - [/test_models/test_file_storage.py](/tests/test_models/test_file_storage.py)
  - [/test_models/test_place.py](/tests/test_models/test_place.py)
  - [/test_models/test_review.py](/tests/test_models/test_review.py)
  - [/test_models/test_state.py](/tests/test_models/test_state.py)
  - [/test_models/test_user.py](/tests/test_models/test_user.py)

## <span style="color:red">_Usage_</span>
vagrantAirBnB_clone$./console.py
(hbnb) help

Documented commands (type help <topic>):
EOF all create destroy help quit show update

(hbnb) all MyModel
** class doesn't exist **
(hbnb) create BaseModel
7da56403-cc45-4f1c-ad32-bfafeb2bb050
(hbnb) all BaseModel
[[BaseModel] (7da56403-cc45-4f1c-ad32-bfafeb2bb050) {'updated_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772167), 'id': '7da56403-cc45-4f1c-ad32-bfafeb2bb050', 'created_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772123)}]
(hbnb) show BaseModel 7da56403-cc45-4f1c-ad32-bfafeb2bb050
[BaseModel] (7da56403-cc45-4f1c-ad32-bfafeb2bb050) {'updated_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772167), 'id': '7da56403-cc45-4f1c-ad32-bfafeb2bb050', 'created_at': datetime.datetime(2017, 9, 28, 9, 50, 46, 772123)}
(hbnb) destroy BaseModel 7da56403-cc45-4f1c-ad32-bfafeb2bb050
(hbnb) show BaseModel 7da56403-cc45-4f1c-ad32-bfafeb2bb050
** no instance found **
(hbnb) quit

## <span style="color:red">_Bugs_</span>
No known bugs at this time.

## <span style="color:red">_Authors_</span>
Alexa Orrico - [Github](https://github.com/alexaorrico) / [Twitter](https://twitter.com/alexa_orrico)
Jennifer Huang - [Github](https://github.com/jhuang10123) / [Twitter](https://twitter.com/earthtojhuang)
Jhoan Zamora - [Github](https://github.com/jzamora5) / [Twitter](https://twitter.com/JhoanZam)
sayed elhadad - [Github](https://github.com/Sayed-Hadad) / [Twitter](https://twitter.com/JhoanZam)
