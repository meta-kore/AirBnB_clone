# AirBnB_clone

The first stage of a student clone of the AirBnB website, written in Python: a command-line console, a data model and JSON file storage, plus the static HTML and CSS for the site.

## Console

```
$ python3 console.py
(hbnb) create User
(hbnb) all User
(hbnb) show User <id>
(hbnb) update User <id> first_name "Jones"
(hbnb) count User
(hbnb) destroy User <id>
(hbnb) quit
```

Commands: `create`, `show`, `all`, `count`, `update`, `destroy`, `quit` (and Ctrl-D). Objects are saved to `file.json`, so they persist between sessions.

## Models

`BaseModel` carries an `id`, `created_at` and `updated_at`, and converts to and from a dictionary. `User`, `State`, `City`, `Amenity`, `Place` and `Review` inherit from it. `models/engine/file_storage.py` serializes everything to JSON and reloads it at start-up.

## Static pages

`web_static/` holds the HTML and CSS for the site, built up over numbered stages (`0-index.html` onward).

## Known issues

The unit tests in `tests/` do not run cleanly as written: running `python3 -m unittest discover tests` gives 55 tests with 50 errors. The test modules instantiate classes at import time (`Place = place.Place()`) and contain typos, so the failures are in the tests, not the models; the console itself works.

## Credits

Written by [Jones Mereu](https://github.com/meta-kore) as a project for ALX Africa Software Engineering. The project follows the AirBnB clone curriculum. Compiled and run on Ubuntu 20.04 LTS.
