# Story 2: In order to track wildlife sightings, as a user of the API, I need to manage animal sightings.

# Branch: sighting-crud-actions

# Acceptance Criteria

---Create a resource for animal sightings with the following information: latitude, longitude, date

Hint: An animal has_many sightings (rails g resource Sighting animal_id:integer ...)

Hint: Date is written in Active Record as yyyy-mm-dd (“2022-07-28")

---Can create a new animal sighting in the database

---Can update an existing animal sighting in the database

---Can remove an animal sighting in the database

class SightingsController < ApplicationController
    def index
        sightings = Sighting.all
        render json: sightings
    end
   

    def create
        sightings = Sighting.create(sighting_params)
        if sightings.save
          render json: sightings
        else
          render json: sighting.errors
        end
    end

    def update
        sightings = Sighting.find(params[:id])
        sightings.update(sighting_params)
        if sightings.valid?
          render json: sightings
        else
          render json: sightings.errors
        end
    end
    
    def destroy
        sightings = Sighting.find(params[:id])
        if sightings.destroy
          render json: sightings
        else
          render json: sightings.errors
        end
    end
private
    def sighting_params
        params.require(:sighting).permit(:latitude, :longitude, :date, :animal_id)
    end
    
end

