const players = [
  {
    name: "Lionel Messi",
    team: "Inter Miami",
    nationality: "Argentina",
    jerseyNumber: 10,
    age: 36,
    image: "https://example.com/messi.jpg"
  },
  {
    name: "Cristiano Ronaldo",
    team: "Al-Nassr",
    nationality: "Portugal",
    jerseyNumber: 7,
    age: 38,
    image: "https://example.com/ronaldo.jpg"
  },
  {
    name: "Kylian Mbappé",
    team: "Paris Saint-Germain",
    nationality: "France",
    jerseyNumber: 7,
    age: 25,
    image: "https://example.com/mbappe.jpg"
  },
  {
    name: "Neymar Jr.",
    team: "Al-Hilal",
    nationality: "Brazil",
    jerseyNumber: 10,
    age: 32,
    image: "https://example.com/neymar.jpg"
  }
];

export default players;


import React from "react";
import { Card } from "react-bootstrap";
import "bootstrap/dist/css/bootstrap.min.css";

function Player({ name, team, nationality, jerseyNumber, age, image }) {
  return (
    <Card style={{ width: "18rem", margin: "10px", boxShadow: "0px 4px 8px rgba(0, 0, 0, 0.2)" }}>
      <Card.Img variant="top" src={image} alt={`${name}`} />
      <Card.Body>
        <Card.Title>{name}</Card.Title>
        <Card.Text>Team: {team}</Card.Text>
        <Card.Text>Nationality: {nationality}</Card.Text>
        <Card.Text>Jersey Number: {jerseyNumber}</Card.Text>
        <Card.Text>Age: {age}</Card.Text>
      </Card.Body>
    </Card>
  );
}

Player.defaultProps = {
  name: "Unknown Player",
  team: "Unknown Team",
  nationality: "Unknown",
  jerseyNumber: 0,
  age: 0,
  image: "https://via.placeholder.com/150"
};

export default Player;


import React from "react";
import Player from "./Player";
import players from "./players";

function PlayersList() {
  return (
    <div style={{ display: "flex", flexWrap: "wrap", justifyContent: "center" }}>
      {players.map((player, index) => (
        <Player key={index} {...player} />
      ))}
    </div>
  );
}

export default PlayersList;

import React from "react";
import PlayersList from "./PlayersList";

function App() {
  return (
    <div className="App">
      <PlayersList />
    </div>
  );
}

export default App;
