# Story 1: In order to track wildlife sightings, as a user of the API, I need to manage animals.

# Branch: animal-crud-actions

Acceptance Criteria

---Create a resource for animal with the following information: common name and scientific binomial

---Can see the data response of all the animals

---Can create a new animal in the database

---Can update an existing animal in the database

---Can remove an animal entry in the database


# Story 2: In order to track wildlife sightings, as a user of the API, I need to manage animal sightings.

# Branch: sighting-crud-actions

# Acceptance Criteria

Create a resource for animal sightings with the following information: latitude, longitude, date

Hint: An animal has_many sightings (rails g resource Sighting animal_id:integer ...)

Hint: Date is written in Active Record as yyyy-mm-dd (“2022-07-28")

Can create a new animal sighting in the database

Can update an existing animal sighting in the database

Can remove an animal sighting in the database