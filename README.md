## README

[See instructions in Alexa.](https://alexa.bitmaker.co/cohorts/67/assignments/2038/latest)

EXERCISES
1. All the Queen Albums:
    Album.where("artist_id = ?", Artist.find_by(name: "Queen"))
    
2. All tracks where the Media type is: Protected Mpeg 4

   Track.where("media_type_id = ?",MediaType.find_by(name: "Protected MPEG-4 video file"))
   
3.Find the Genre hip hop rap
        Genre.find_by(name: "Hip Hop/Rap")

4. Number of Tracks that are Hiphop/rap
        Track.where("genre_id = ?", Genre.find_by(name: "Hip Hop/Rap")).count
        
5. total amount of time required to listen to all the tracks in the database.
    Track.sum('milliseconds')
    
    
6. highest price of any track that has the media type "MPEG audio file".

      Track.where("media_type_id = ?", MediaType.find_by(name: "MPEG audio file")).maximum('unit_price')

7. Find the name of the most expensive track that has the media type "MPEG audio file".
      Track.where("media_type_id = ?", MediaType.find_by(name: "MPEG audio file")).order(:unit_price).last.name

8. 2 oldest artists
    Artist.order(:created_at).first(2)

9. Cheapest Electronica Track
    Track.order(:unit_price).where("genre_id = ?", Genre.find_by(name: 'Electronica/Dance')).first

10. Track.select(:name).where("media_type_id = ? AND genre_id = ?" , MediaType.find_by(name: "MPEG audio file"), Genre.find_by(name: "Electronica/Dance"))


STRETCH

1. Album.where('title LIKE ?', 'B%')

2. Artist.where('name LINE ?', 'A%')


  
