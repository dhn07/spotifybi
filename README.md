## Spotify Artist Card - A Mini Project

In this mini project, the goal was to create a Spotify Artist Card that displays some information about that artist.
The data was sourced from [Kaggle](https://www.kaggle.com/datasets/irynatokarchuk/top-streamed-spotify-songs-by-year-2010-2023). 
One of the enjoyable elements of using PowerBI and similar tools is how visceral the feedback is given that it's mostly a visual medium. I definitely played on the visual and thematic elements of the project.

![coldplay](https://github.com/user-attachments/assets/97a6d4fb-eba6-4f4f-908f-924c8f85dc9a)
![adele](https://github.com/user-attachments/assets/7af2d83a-822b-4073-a6b1-2551256e17a1)
![eminem](https://github.com/user-attachments/assets/e182e7e8-dce2-4936-8871-aa6398f2890a)
![blackpink](https://github.com/user-attachments/assets/6da2211f-7de7-414f-b54b-85d012446169)


---

#### Search Slicer

The main functionality of the dashboard is to select an artist via the drop down slicer through scrolling or text searching. After selecting the artist, the information for that artist will appear. A very simple tool with many ways to upgrade and iterate over time. 

![searchbar](https://github.com/user-attachments/assets/f3f44657-2d22-44c6-9ee2-fab125ca1c9b)



---

#### Measures

Due to the way PowerBI is, we use DAX code in measures to help us obtain the variables we need to display. In this case, in order to isolate the most popular song and it's corresponding data, we need to use a measure and the `calculate` function. This allows it to condense the column which is a vector into a scalar.

```DAX
TopSong = 
CALCULATE(
    FIRSTNONBLANK(spotify_full_list_20102023[Artist and Title], 1),
    spotify_full_list_20102023[Streams] = MAX(spotify_full_list_20102023[Streams])
)
```

---

I hope you enjoyed this proof of concept in PowerBI. Feel free to reach out to me with any enquiries or just to say hello.

- [GitHub](https://github.com/danstands)
- [LinkedIn](https://www.linkedin.com/in/dhn07/)
