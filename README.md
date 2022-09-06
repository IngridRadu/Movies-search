# Movie Search App
A React application where users can search for a movie.

## Download the code
https://github.com/IngridRadu/Movies-search.git

## Install
npm start

## Quick Look
App component

```
import React from "react";
import SearchBar from "./SearchBar";
import { getMovies } from "../apis/movies";
import MovieList from "./MovieList";

class App extends React.Component {
  state = { movies: [] };

  onTermSubmit = async (term) => {
    const result = await getMovies(term);

    this.setState({ movies: result.results });
  };

  render() {
    return (
      <div className="container">
        <SearchBar onFormSubmit={this.onTermSubmit} />
        <MovieList movies={this.state.movies} />
      </div>
    );
  }
}

export default App;
```
